<title>Conversation Category</title>
<h1>Conversation Category</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import { goto } from '$app/navigation'
    import { onMount } from "svelte";

    let key;
    //Audio Files, however category has no audio files

	function handleKeydown(event) {
		key = event.key;
        if(key == 0){
            goto('home');
        }

        if(key == 1){
            goto('/asking');
        }

        if(key == 2){
            goto('/sharing_and_responding')
        }
	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <PhraseOptions num=0 description="Exit"/>
    <PhraseOptions num=1 description="Asking"/>
    <PhraseOptions num=2 description="Sharing/Responding"/>
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