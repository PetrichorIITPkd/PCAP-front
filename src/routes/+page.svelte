<div class="banner">
    <h1 class="title petr">PETRICHOR</h1>
    <h2 class="subheading"> THE CA PROGRAM  </h2>
</div>
<div class="content">
    <div class="btns">
        <a href="/onboard" type="text" class="tp-field input" data-underline="--accent">Sign Up</a>
        <a href="/login" type="text" class="tp-field input" >Log in</a>
    </div>
    <p>30k Prize Pool</p>
    <p>Earn more for each registration/participation you bring</p>
</div>
<div class="marketingbs">
    <div class="card">
        <h2>Benefits</h2>
        <li>Win cash prizes from a pool of 30k if you are in the top 5 CAs </li>
        <li>Earn ₹ 50 per extra registration above 5 (for workshops and tech summit)</li>
        <li>Win exciting goodies and pro-show tickets of Petrichor'24</li>
        <li>Earn certificate of merit issued by Petrichor, IIT Palakkad for your valiant efforts</li>
        <li>Get referral codes that participants can use that to avail a flat 10% discount for workshops!</li>
    </div>
    <div class="card neg">
        <h2>All You Have to do</h2>
        <li>Share our content, posters and links to your peers and college groups</li>
        <li>Encourage students from your college and contacts to participate in our events and workshops</li>
    </div>
</div>
<!-- <div class="i"> -->
<!-- </div> -->
<!-- <span>Frontend by <a href="https://github.com/enchanteddev" style="color: lightblue;">Kaushik</a></span> -->
<style>
    .marketingbs{
        margin-left: 2vw;
        width: 90%;
        display: flex;
        margin-bottom: 3em;
    }
    .card{
        width: 50%;
        height: 30em;
        padding: 2em;
        background-color: white;
        color:black;
    }
    .neg{
        background-color: black;
        color: white
    }
    .card > h2{
        font-size: 48px;
    }
    .card > li{
        font-size: 24px;
        margin-left: 2em;
        margin-bottom: 1em;
    }
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
        position: relative;
        font-size: 15vw;
        transition: 200ms ease-in-out;
        margin: 0;
        color: var(--accent);
        /* background: linear-gradient(140deg, var(--accent-dark), var(--accent), var(--accent-light), var(--accent),  var(--accent-light)); */
        background-size: 200% 200%;
        /* -webkit-background-clip: text; */
        /* -webkit-text-fill-color: transparent; */
        /* animation: gradanim 3s ease-in-out infinite; */

        
    }
    .petr:hover::after{
        bottom: -1rem;
    }
    .petr:hover::before{
        bottom: -2rem;
    }
    .petr::after{
        content: "PETRICHOR";
        position: absolute;
        text-shadow: -1px -1px 0 #FFF9, 1px -1px 0 #FFF9, -1px 1px 0 #FFF9, 1px 1px 0 #FFF9;
        color: black;
        z-index: -1;
        left: 0;
        bottom: -0.5rem;
        transition: 100ms ease-in-out;
    }
    .petr::before{
        content: "PETRICHOR";
        position: absolute;
        text-shadow: -1px -1px 0 #FFF5, 1px -1px 0 #FFF5, -1px 1px 0 #FFF5, 1px 1px 0 #FFF5;
        color: black;
        z-index: -1;
        left: 0;
        bottom: -0.95rem;
        transition: 100ms ease-in-out;
    }
    .subheading{
        margin: 0;
        font-size: 6vw;
        font-weight: normal;
        color: var(--accent-light);
    }
    .petr:hover{
        /* transform: skew(-8deg); */
    }
    .btns{
        margin-top: 2em;
        margin-bottom: 2em;
        display: flex;
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
        display: block;
        width: 5em;
        text-align: center;
        margin: 1em;
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
        /* background-image: url("favicon.ico"); */
        z-index: 0;
        filter:brightness(21%);
        background-size: 2%;
        animation: anim 40s infinite linear;
    }
    @media (max-width: 1000px){
        .petr{
            margin-top: 1em;
            margin-bottom: .5em;
        }
        .content{
            width: 90%;
        }
        .input{
            width: 4em;
            margin: 0;
            margin-inline: 0.2em;
            font-size: 24px;
            margin-top: 2em;
            margin-bottom: 4em;
        }
        .btns{
            margin-top: 0;
        }
        /* .content > p{
            width: 95%;
            text-align: justify;
            font-size: 20px;
            position: absolute;
            bottom: 0;
        } */
        .i{
            background-size: 10%;
            animation-duration: 20s;
        }
        .marketingbs{
            display: block;
        }
        .card{
            width: 80%;
            height: max-content;
        }
        .card > li{
            margin-left: 0.6em;
            font-size: 15px;
        }
    }
</style>