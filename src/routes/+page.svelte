<div class="banner">
    <h1 class="title petr">PETRICHOR</h1>
    <h2 class="subheading">// THE CA PROGRAM //</h2>
</div>
<div class="content">
    <a href="/onboard" type="text" class="tp-field input">Join us as a <span style="color: red;">campus ambassador</span> now</a>
    <p>Your chance to be the know-it-all, go-to person for Petrichor'23 at your institution! Plus, exciting perks await those who ask work for it!!</p>
</div>

<style>
    .content{
        margin-left: 2vw;
        width: 60%;
        font-size: 24px;
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .banner{
        display: flex;
        flex-direction: column;
        align-items: center;

    }
    .petr{
        font-size: 15vw;
        transition: 200ms ease-in-out;
        margin: 0;
        
    }
    .subheading{
        margin: 0;
        font-size: 6vw;
        font-weight: normal;
    }
    .petr:hover{
        transform: skew(-8deg);
    }
    .input{
        border: 0.05em solid var(--fg-color);
        /* width: 80%; */
        font: inherit;
        font-size: 48px;
        margin-top: 2em;
        margin-bottom: 2em;
        padding: 0.5em;
        padding-inline: 1em;
        cursor: pointer;
        transition: 200ms ease-in-out;
        position: relative;
        text-decoration: unset;
    }
    .input::before{
        transition: 200ms ease-in-out;
        content: "";
        position: absolute;
        width: 0;
        height: 0.1em;
        font-size: inherit;
        background-color: white;
        bottom: 0.3em;
        left: 1em;
    }
    .input:hover::before{
        width: calc(100% - 2em);
    }
    .input:hover{
        border-radius: .3em;
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
            width: 100%;
            text-align: justify;
            font-size: 20px;
        }
        
    }
</style>