<!--This File simply serves as our iniital template page that Reid taught us with-->

<script>
    import Example from "../components/example.svelte";


    let x = 0;

    function handleClick(){
        x++;
    }

    //https://svelte.dev/tutorial/svelte-window 
    let key;
    function handleKeydown(event){
        key = event.key;
        if(key == 1){
            //play phrase 1
        }
    }
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<Example />

<button on:click={handleClick}>Clicked on {x} times</button>
<svelte:window on:keydown={handleKeydown}/>
<p>{key}</p>


<style>
    h1 {
        color: red;
    }
</style>