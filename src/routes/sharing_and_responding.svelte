<title>Sharing and Responding</title>
<h1>Sharing and Responding Phrases</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import { goto } from '$app/navigation'
    import { onMount } from "svelte";
    import Exitphraseoptions from "../components/exitphraseoptions.svelte";

    let key;
    //Audio files

	function handleKeydown(event) {
		key = event.key;
        if(key == 0){
            goto('home');
        }

        if(key == 1){
            thanks.play();
        }

        if(key == 2){
            sorry.play();
        }
        
        if(key == 3){
            excuseme.play();
        }

        if(key == 4){
            hello.play();
        }
	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <Exitphraseoptions num=0 description="I am well"/>
    <PhraseOptions num=1 description="I am not well"/>
    <PhraseOptions num=2 description="I am so-so wel"/>
    <PhraseOptions num=3 description="It is good to see you too"/>
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