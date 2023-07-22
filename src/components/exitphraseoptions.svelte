<script>
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();

    export let num = 0;
    export let description = "null";
    
    function clicked(){
        dispatch('clicked');
    }
</script>


<button class="exit-main-button" on:click={clicked}>
    <span>{num}</span>
    <span>{description}</span>
</button>


<br>


<style>
    .exit-main-button{  
        border: 0.25px solid white;
        background-color: #969696;
        color: white;
        text-align: left;
        border-radius: 10px;
        padding: 10px;
        font-size: 24px;
        margin: 10px 0px;
        min-width: 275px;
        max-width: 275px;
        font-family: "Inter";
        box-shadow: 0 4px 6px rgba(50, 50, 93, 0.11), 0 1px 3px rgba(0, 0, 0, 0.08);
    }
</style>

