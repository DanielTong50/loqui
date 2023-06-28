<script>
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();

    export let num = 0;
    export let description = "";
    export let icon;
    
    function clicked(){
        dispatch('clicked');
    }
</script>

<button class="main-button" on:click={clicked}>
    <div class="icon"><i class="fa-solid fa-{icon} fa-lg icon" /></div>
    <div class="content">
        <span class="number">{num}</span>
        <span class="text">{description}</span>
    </div>
    
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
    
    .number {
        margin-right: 10px;
    }
</style>

