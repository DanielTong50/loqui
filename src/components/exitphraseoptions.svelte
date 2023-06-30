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
        border: 1px solid black;
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
    }
</style>

