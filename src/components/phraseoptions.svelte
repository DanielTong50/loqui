<script>
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();

    export let num = 0;
    export let description = "null";
    export let icon = "";
    

    function clicked(){
        dispatch('clicked');
    }


</script>


<button class="main-button" on:click={clicked}>
    <span>{num}</span>
    <span>{description}</span>
    <img src="/icons/{icon}" alt="">
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
    .main-button img {
        height: 30px;
    }
</style>