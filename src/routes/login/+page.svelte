<script>
    // import {validateusername} from '$lib/validate.js'
    import {API_URL, API} from '$lib/api.js'
    import Profile from './profile.svelte';

    let username;
    let password;

    let loggedIN = false;

    let user_data = {
        name: '',
        CA: "",
        registrations: ''
    }

    const login = async () => {
        const response = await fetch(API_URL + API.login, {
            method: "POST",
            headers: {
                "Content-Type": "application/json",
            },

            body: JSON.stringify({
                username: username,
                password: password
            })
        })

        const result = await response.json();
        if (result.ok){
            loggedIN = true;
            user_data.name = result.username;
            user_data.CA = result.CA;
            user_data.registrations = result.registrations;
        } else {
            alert("Username or Password is incorrect")
            console.log(result)
        }
    }

</script>

{#if !loggedIN}    
    <div class="main">
        <div class="header">
            <img src="/favicon.ico" alt=""> <span>Welcome Back <span style="color: var(--accent);">CA!</span></span>
        </div>
        <div class="content">
            <form on:submit|preventDefault class="container">
                <div class="input-cont">
                    <div class="heading">email</div>
                    <div class="input">
                        <input type="text" placeholder="enter your email" class="tp-field inputbox" bind:value={username}>
                    </div>
                    <!-- <div class="validation" style="color: red;">{validation}</div> -->
                </div>
                <div class="input-cont">
                    <div class="heading">password</div>
                    <div class="input">
                        <input type="password" placeholder="enter your password" class="tp-field inputbox" bind:value={password}>
                    </div>
                    <!-- <div class="validation" style="color: red;">{validation}</div> -->
                </div>
                <button class="tp-field input" style="cursor: pointer;" on:click={() => {
                    // if (!validateusername(username)){
                    //     alert("That username doesn't seem right. Check again")
                    // } else {
                        login()
                    // }
                }}>Log In!</button>
            </form>
        </div>
    </div>
{:else}
    <Profile {...user_data}/>
{/if}
<style>
    .input-cont{
        width: 100%;
        margin-bottom: 3em;
    }
    .container{
        width: 60%;
    }
    .heading{
        font-size: 36px;
        /* margin-left: 1em; */
        margin-bottom: 0.5em;
        color: var(--accent-light)
    }
    .input{
        border: 2px solid var(--fg-color);
        font-weight: 200;
        border-radius: .3em;
        font-size: 36px;
        padding: 0.5em;
        padding-inline: 1em;
        display: flex;
        margin-bottom: 0.3em;
    }
    .inputbox{
        width: 100%;   
    }
    .submitbutton{
        cursor: pointer;
    }
    .main{
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 50em;
        height: 40em;
        background-color: var(--accent-dark);
        border-radius: 2em;
        padding: 2em;
        display: flex;
        flex-direction: column;
    }
    .content{
        flex-grow: 1;
        display: grid;
        place-items: center;
    }
    .header{
        display: flex;
        align-items: center;
        font-size: 48px;
    }
    .header>span{
        margin-left: .2em;
        height: 0.8em;
    }

    @media (max-width: 1000px){
        .container{
            width: 100%;
        }
        .main{
            width: 95%;
            background-color: black;
        }
        .header{
            font-size: 40px;
        }
        .input{
            font-size: 30px;
        }
        .main{
            position: relative;
            top: unset;
            left: unset;
            transform: unset;
        }
    }
</style>