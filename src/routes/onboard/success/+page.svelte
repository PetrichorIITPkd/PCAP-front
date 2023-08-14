<div class="main">
    <h1>Registered Successfully</h1>
    <p>You will now recieve an email on your email address. <a href="/login">Login</a> after you have verified your email via the welcome mail</p>

</div>

<style>
    .main{
        background-image: url('$lib/public/mail.gif');
        height: 100vh;
        filter: invert(1);
        background-repeat: no-repeat;
        background-position: center;
        background-size: 50%;
        color: black;
    }
    h1{
        font-size: 7vw;
        /* margin-top: 10rem; */
        margin: 0;
        margin-bottom: -1rem;
        text-align: center;
        color: rgb(201, 8, 201);
    }
    p{
        font-size: 3vw;
        width: 90%;
        text-align: center;
        position: absolute;
        bottom: 0;
    }
    a{
        text-decoration: none;
        color: rgb(36, 255, 36);
        position: relative;
        z-index: 0;
        transition: 100ms ease-in-out;
    }
    a::after{
        position: absolute;
        content: "";
        bottom: -5px;
        left:0;
        width: 100%;
        height: 5px;
        background-color: black;
        z-index: -1;
        transition: inherit;
    }
    a:hover::after{
        background-color: rgb(36, 255, 36);
        height: calc(100% + 10px);
    }
    a:hover{
        color: black;
    }

    @media (max-width: 1000px){
        p{
            text-align: justify;
            font-size: 2em;
            width: 100%;
        }
        h1{
            margin-top: 2em;
        }
    }
    
</style>