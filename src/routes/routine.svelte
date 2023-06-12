<title>Routine</title>
<h1>Routine Phrases</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import { goto } from '$app/navigation'
    import { onMount } from "svelte";
    import Exitphraseoptions from "../components/exitphraseoptions.svelte";

    let key;
    //Audio files
    let GoodMorning = new Audio("./audio/GoodMorning.m4a")
    let GoodAfternoon = new Audio("./audio/GoodAfternoon.m4a")
    let GoodEvening = new Audio("./audio/GoodEvening.m4a")
    let GoodNight = new Audio("./audio/GoodNight.m4a")

	function handleKeydown(event) {
		key = event.key;
        selectPhrase(key);
    }

    function selectPhrase(num) {
        if(num == 0){
            goto('socializing');
        }

        if(num == 1){
            GoodMorning.play();
        }

        if(num == 2){
            GoodAfternoon.play();
        }
        
        if(num == 3){
            GoodEvening.play();
        }

        if(num == 4){
            GoodNight.play();
        }
	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <Exitphraseoptions num=0 description="Exit" on:clicked={() => {selectPhrase(0)}}/>
    <PhraseOptions num=1 description="Good morning" on:clicked={() => {selectPhrase(1)}}/>
    <PhraseOptions num=2 description="Good afternoon" on:clicked={() => {selectPhrase(2)}}/>
    <PhraseOptions num=3 description="Good evening" on:clicked={() => {selectPhrase(3)}}/>
    <PhraseOptions num=4 description="Good night" on:clicked={() => {selectPhrase(4)}}/>

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