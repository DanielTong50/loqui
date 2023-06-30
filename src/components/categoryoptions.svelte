<script>
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();

    export let num = 0;
    export let description = "null";
    export let img = 'null';
    

    function clicked(){
        dispatch('clicked');
    }
</script>


<button class="main-button" on:click={clicked}>
    <img  src = {img} alt="ImageSoon" class = "icon"/>
    <br>
    <span>{num}</span>
    <span>{description}</span>
    

</button>


<br>


<style>
    .main-button{  
        font-family: "Poppins", sans-serif;
        border: 1px solid black;
        background-color: #40C2E1;
        color: white;
        text-align: left;
        border-radius: 10px;
        padding: 10px;
        font-size: 24px;
        margin: 10px 0px;
        min-width: 275px;
        max-width: 275px;
    }
    .icon {
        display: block;
        margin-left: auto;
        margin-right: auto;
        width: 50%;
}

</style>

