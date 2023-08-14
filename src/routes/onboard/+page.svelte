<script>
    import {validateEmail} from '$lib/validate.js'
    import {API_URL, API} from '$lib/api.js'
    let data = {
        "name": "",
        // "college": "",
        "email": "",
        "phone": "",
        "college": "",
        "current year of degree": "", 
        "password": "",
        "password (again)": ""
    };
    let steps = Object.keys(data);
    let step = 0;
    let current_step = steps[step];
    $: current_step = steps[step];
    let current_temp;

    const back = () => {
        if(step == 0){return}
        step--;
        current_temp = data[steps[step]];
        console.log(current_temp)
    }
    

    let validation = "";
    const validate = (temp) => {
        let val = "";
        if (current_step == "password (again)"){
            console.log(current_temp, data[steps[step - 1]])
            if (temp != data[steps[step - 1]]){
                val = "Passwords do not match"
            }
        } else if (current_step == "email"){
            if (!validateEmail(current_temp)){
                val = "Not A Valid Email"
            }
        }
        else if (current_step == "phone"){
            if (current_temp < 1000000000 || current_temp > 9999999999){
                val = "Not a valid phone number. Please dont include +91"
            }
        }
        else if (current_step == "current year of degree"){
            if (Number(current_temp) > 6){
                val = "year of study should be less than or equal to 6 "
            }
        }

        return val;
    }

    $: { // input validation
        if (validation){
            validation = validate(current_temp);
        }
    }

    const register = async () => {
        const response = await fetch(API_URL + API.register, {
            "method": "POST",
            headers: {
                "Content-Type": "application/json",
            },

            body: JSON.stringify({
                username: data.name,
                password: data.password,
                phone: data.phone,
                email: data.email,
                college: data.college,
                year: data["current year of degree"]
            })
        })

        const result = await response.json();
        console.log(result)
        if (result.registered){
            window.location.replace('/onboard/success')
        }
    }
</script>

<div class="main">
    <div class="header">
        <button class="backbtn" on:click={back}>←</button>
        <span class="progress" style="width: calc({(step + 1) / steps.length} * (100% + 4rem));"></span>
        <img src="/favicon.ico" alt="">
        <span class="h1">Petrichor <span style="color: var(--accent);">CA</span> Sign Up</span>
    </div>
    <div class="content">
        <div class="input-cont">
            <div class="heading">{current_step}</div>
            <div>
                <form on:submit|preventDefault class="input">
                    {#if current_step.includes("pass")}
                        <input type="password" placeholder="enter your {current_step}" class="tp-field inputbox" bind:value={current_temp}>
                        {:else}

                        <input type="text" placeholder="enter your {current_step}" class="tp-field inputbox" bind:value={current_temp}>
                    {/if}
                    <button class="tp-field submitbutton" on:click={() => {
                        validation = validate(current_temp);
                        console.log(validation)
                        if (validation != ""){return}
                        data[steps[step]] = current_temp;
                        if (step < steps.length - 1){
                            step++;
                            current_temp = "";
                            console.log(data)
                        } else {
                            console.log(data, "send to api");
                            register()
                        }
                    }}> → </button>
                </form>
            </div>
            <div class="validation" style="color: red;">{validation}</div>
        </div>
    </div>
</div>
<style>
    .input-cont{
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
        position: relative;
    }
    .header>.h1{
        margin-left: .2em;
        height: 0.8em;
    }
    .backbtn{
        border-radius: 100%;
        aspect-ratio: 1;
        width: 1.2em;
        background-color: white;
        border: none;
        outline: none;
        cursor: pointer;
        margin-right: 1em;
    }
    .progress{
        position: absolute;
        background-color: lightblue;
        /* width: calc(100% + 4rem); */
        height: 3px;
        margin-left: -2rem;
        bottom: -.5em;
        transition: 200ms ease-in-out;
    }
    @media (max-width: 1000px){
        .input-cont{
            width: 100%;
        }
        .main{
            width: 90%;
            height: 25em;
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