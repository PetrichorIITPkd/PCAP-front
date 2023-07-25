<script>
    let data = {
        "name": "",
        "college": "",
        "email": "",
        "password": "",
        "password (again)": ""
    };
    let steps = Object.keys(data);
    let step = 0;
    let current_step = steps[step];
    $: current_step = steps[step];
    let current_temp;

    function validateEmail(email) {
        const re = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
        return re.test(String(email).toLowerCase());
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

        return val;
    }

    $: { // input validation
        if (validation){
            validation = validate(current_temp);
        }
    }
</script>

<div class="main">
    <div class="header">
        <img src="/favicon.ico" alt=""> <span>Petrichor <span style="color: red;">CA</span> Sign Up</span>
    </div>
    <div class="content">
        <div class="input-cont">
            <div class="heading">{current_step}</div>
            <div class="input">
                <input type="text" placeholder="enter your {current_step}" class="tp-field inputbox" bind:value={current_temp}>
                <button class="tp-field submitbutton" on:click={() => {
                    validation = validate(current_temp);
                    console.log(validation)
                    if (validation != ""){return}
                    if (step < steps.length - 1){
                        data[steps[step]] = current_temp;
                        step++;
                        current_temp = "";
                        console.log(data)
                    } else {}
                }}> > </button>
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
        background-color: rgb(16, 16, 16);
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
</style>