<script>
    export let name;
    export let email;
    export let phone;
    export let ca;
    export let college;
    export let year;
</script>
<div class="main">
    <h1>{name} | <span class="ca">{ca}</span></h1>
    <p class="details">{email}</p>
    <p class="details">{phone}</p>
    <p class="details">year {year} @ {college}</p>
</div>

<style>
    .main{
        width: 90vw;
        margin-left: 5vw;
        margin-right: 5vw;
        max-width: 50em;
        position: relative;
    }
    .info{
        width: 100%
    }
    .ca{
        font-weight: 200;
        border: 1px solid white;
        padding: 0.15em;
        padding-inline: .3em;
        border-radius: 1em;
        display: inline-block;
        margin-top: .1em;
    }
</style>