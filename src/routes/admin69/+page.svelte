<script>
    import {API_URL, API} from '$lib/api.js'
    import Caprofile from './caprofile.svelte';
    let password = "";
    let loggedin = false;
    let cas = []
    const letmein = async() => {
        const response = await fetch(API_URL + API.admin, {
            method: "POST",
            headers: {
                "Content-Type": "application/json",
            },

            body: JSON.stringify({
                password: password
            })
        })
        const result = await response.json()
        if (result.status == 200){
            loggedin = true;
            cas = result.data;
        } else if (result.status == 500){
            alert(result.message)
        }
    }
</script>

{#if !loggedin}
    <form on:submit|preventDefault={letmein}>
        <input type="password" class="tp-field" placeholder="???" bind:value={password}>
    </form>
{:else}
<h1>THE CAs [Real Time Data]</h1>
{#each cas as cap}
    <Caprofile {...cap}/>
{/each}
{/if}

<style>
    form{
        display: grid;
        place-items: center;
        height: 100vh;
    }
    input{
        border: 2px solid white;
        padding: 0.5em;
        padding-inline: 1em;
        font-size: 24px;
        backdrop-filter: blur(3px);
    }
</style>