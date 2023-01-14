<script>
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();

    export let num = 0;
    export let description = "null";


    

    function clicked(){
        dispatch('clicked');
    }


</script>


<button class="main-button" on:click={clicked}>
    <span>{num}</span>
    <span>{description}</span>
</button>


<style>
    .main-button{
        background-color: #40C2E1;
        color: white;
        /* text-align: center; */
        border-radius: 10px;
        padding: 10px;
        font-size: 24px;
        margin: 20px 0px;
    }
</style>