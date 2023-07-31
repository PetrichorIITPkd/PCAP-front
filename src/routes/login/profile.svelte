<script>
    export let name;
    export let CA;
    export let registrations;
</script>
<div class="main">
    <h1>Hi <span style="color:red">{name}!</span></h1>
    <hr>
    <div class="info">
        <div class="col">
            <div class="card">
                <div class="heading">Your CA Code</div>
                <div class="main">{CA}</div>
            </div>
            <div class="card">
                <div class="heading">Total Registrations</div>
                <div class="main">{registrations}</div>
            </div>
        </div>
    </div>
</div>

<style>
    .main{
        width: 90%;
    }
    h1{
        font-size: 98px;
        margin-bottom: 0;
    }
    .info{
        display: flex;
    }
    .col{
        margin-right: 1em;
    }
    .card{
        background-color: rgb(38, 38, 38);
        min-width: 20em;
        max-width: 90vw;
        padding: 1em;
        border-radius: 1em;
        margin-bottom: 1em; 
        margin-top: 1em; 
    }
    .card > .heading{
        color: rgb(188, 188, 188);
        margin-bottom: 1em;
    }
    .card > .main{
        font-size: 88px;
        width: fit-content;
    }
</style>