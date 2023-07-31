<div class="banner">
    <h1 class="title petr">PETRICHOR</h1>
    <h2 class="subheading">// THE CA PROGRAM //</h2>
</div>
<div class="content">
    <div class="btns">
        <a href="/onboard" type="text" class="tp-field input">Sign Up</a>
        <a href="/login" type="text" class="tp-field input" data-underline="--accent">Log in</a>
    </div>
    <p>Your chance to be the know-it-all, go-to person for Petrichor'23 at your institution! Plus, exciting perks await those who ask work for it!!</p>
</div>
<div class="i">
</div>

<style>
    .content{
        margin-left: 2vw;
        width: 60%;
        font-size: 24px;
        display: flex;
        flex-direction: column;
        align-items: center;
        z-index: 3;
    }
    .banner{
        display: flex;
        flex-direction: column;
        align-items: center;
        z-index: 3;
    }
    /* @keyframes gradanim {
        0%{background-position:0% 0%}
        50%{background-position:100% 100%}
        100%{background-position:0% 0%}
    } */
    .petr{
        font-size: 15vw;
        transition: 200ms ease-in-out;
        margin: 0;
        background: linear-gradient(140deg, var(--accent-dark), var(--accent), var(--accent-light), var(--accent),  var(--accent-light));
        background-size: 200% 200%;
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        /* animation: gradanim 3s ease-in-out infinite; */

        
    }
    .subheading{
        margin: 0;
        font-size: 6vw;
        font-weight: normal;
        color: var(--accent-light);
    }
    .petr:hover{
        transform: skew(-8deg);
    }
    .btns{
        margin-top: 2em;
        margin-bottom: 2em;
    }
    .input{
        /* border: 0.05em solid var(--fg-color); */
        /* width: 80%; */
        font: inherit;
        font-size: 48px;
        padding: 0.5em;
        padding-inline: 1em;
        cursor: pointer;
        transition: 200ms ease-in-out;
        position: relative;
        text-decoration: unset;
        /* background-color: black; */
        border: white 2px solid;
        border-radius: .5em;
    }
    /* .input::before{
        transition: 200ms ease-in-out;
        content: "";
        position: absolute;
        width: 0;
        height: 0.1em;
        font-size: inherit;
        background-color: white;
        bottom: 0.3em;
        left: 1em;
    } */
    .input[data-underline]{
        background-color: var(--accent);
        border-color: var(--accent);
    }
    .input[data-underline]:hover{
        background-color: white;
        border-color: white;
        color: var(--accent)
    } 
    .input:hover::before{
        width: calc(100% - 2em);
    }
    .input:hover{
        border-color: var(--accent);
        color: var(--accent)
        /* background-color: var(--accent); */
    }

    @keyframes anim {
        from{

        }
        to{
            background-position: 100%;
        }
    }
    .i{
        position: absolute;
        top: 0;
        height: 100svh;
        border: 1px solid white;
        width: 100%;
        background-image: url("favicon.ico");
        z-index: 0;
        filter:brightness(21%);
        background-size: 2%;
        animation: anim 40s infinite linear;
    }
    @media (max-width: 1000px){
        .petr{
            margin-top: 1.5em;
        }
        .content{
            width: 90%;
        }
        .input{
            width: 90%;
            font-size: 24px;
            margin-top: 4em;
            margin-bottom: 1em;
        }
        .content > p{
            width: 95%;
            text-align: justify;
            font-size: 20px;
            position: absolute;
            bottom: 0;
        }
        .i{
            background-size: 10%;
            animation-duration: 20s;
        }
    }
</style>