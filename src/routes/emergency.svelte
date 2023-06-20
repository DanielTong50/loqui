<title>Emergency Category</title>
<h1>Emergency Category</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import CategoryOptions from "../components/categoryoptions.svelte"
    import { goto } from '$app/navigation'
    import { onMount } from "svelte";
    import Exitphraseoptions from "../components/exitphraseoptions.svelte";
    let key;
    //Audio Files, however category has no audio files

	function handleKeydown(event) {
		key = event.key;
        selectPhrase(key)
    }

    function selectPhrase(num)
    {
        if(num == 0){
            goto('/home');
        }

       else if(num == 1){
            goto('/mild');
        }

        else if(num == 2){
            goto('/severe');
        }
	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <Exitphraseoptions num=0 description="Exit" on:clicked={() => {selectPhrase(0)}}/>
    <CategoryOptions num=1 description="Mild" img = "mild.png" on:clicked={() => {selectPhrase(1)}}/>
    <CategoryOptions num=2 description="Severe" img = "severe.png" on:clicked={() => {selectPhrase(2)}}/>
</div>

<div class = "instructions">
    <p>Press the number corresponding to the phrase option. Press 0 anytime to return to the home page.</p>
</div>

<style>
    .instructions {
        color: gray;
        font-style: italic;
    }
</style>