<title>Thanking</title>
<h1>Thanking Phrases</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import { goto } from '$app/navigation'
    import { onMount } from "svelte";
    import Exitphraseoptions from "../components/exitphraseoptions.svelte";

    let key;
    //Audio files
    let ThankYou = new Audio("./audio/ThankYou.mp3")
    let Appreciate = new Audio("./audio/Appreciate.mp3")
    let VeryHelpful = new Audio("./audio/Veryhelpful.mp3")

	function handleKeydown(event) {
		key = event.key;
        selectPhrase(key);
    }

    function selectPhrase(num) {
        if(num == 0){
            goto('socializing');
        }

        if(num == 1){
            ThankYou.play();
        }

        if(num == 2){
            Appreciate.play();
        }
        
        if(num == 3){
            VeryHelpful.play();
        }
	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <Exitphraseoptions num=0 description="Exit" on:clicked={() => {selectPhrase(0)}}/>
    <PhraseOptions num=1 description="Thank you" on:clicked={() => {selectPhrase(1)}}/>
    <PhraseOptions num=2 description="I appreciate it" on:clicked={() => {selectPhrase(2)}}/>
    <PhraseOptions num=3 description="You have been very helpful" on:clicked={() => {selectPhrase(3)}}/>

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