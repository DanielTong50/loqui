<title>Mild</title>
<h1>Mild Phrases</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import { goto } from '$app/navigation'
    import { onMount } from "svelte";
    import Exitphraseoptions from "../components/exitphraseoptions.svelte";
	import Phraseoptions from "../components/phraseoptions.svelte";

    let key;
    //Audio files
    let HeadHurts = new Audio("./audio/HeadHurts.mp3")
    let ArmsHurt = new Audio("./audio/ArmsHurt.mp3")
    let ArmHurts = new Audio("./audio/ArmHurts.mp3")
    let BackHurts = new Audio("./audio/BackHurts.mp3")
    let LegsHurt = new Audio("./audio/LegsHurt.mp3")
    let ChestHurts = new Audio("./audio/ChestHurts.mp3")
    let FeetHurt = new Audio("./audio/FeetHurt.mp3")
    let EyesHurt = new Audio("./audio/EyesHurt.mp3")

	function handleKeydown(event) {
		key = event.key;
        selectPhrase(key);
    }

    function selectPhrase(num) {
        if(num == 0){
            goto('emergency');
        }

        if(num == 1){
            HeadHurts.play();
        }

        if(num == 2){
            ArmsHurt.play();
        }
        
        if(num == 3){
            ArmHurts.play();
        }

        if(num == 4){
            BackHurts.play();
        }

        if(num == 5){
            LegsHurt.play();
        }

        if(num == 6){
            ChestHurts.play();
        }

        if(num == 7){
            FeetHurt.play();
        }

        if(num == 8){
            EyesHurt.play();
        }
	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <Exitphraseoptions num=0 description="Exit"  on:clicked={() => {selectPhrase(0)}}/>
    <PhraseOptions num=1 description="My head hurts"  on:clicked={() => {selectPhrase(1)}}/>
    <PhraseOptions num=2 description="My arms hurt"  on:clicked={() => {selectPhrase(2)}}/>
    <PhraseOptions num=3 description="My arm hurts"  on:clicked={() => {selectPhrase(3)}}/>
    <PhraseOptions num=4 description="My back hurts"  on:clicked={() => {selectPhrase(4)}}/>
    <PhraseOptions num=5 description="My legs hurts"  on:clicked={() => {selectPhrase(5)}}/>
    <PhraseOptions num=6 description="My chest hurts"  on:clicked={() => {selectPhrase(6)}}/>
    <PhraseOptions num=7 description="My feet hurt"  on:clicked={() => {selectPhrase(7)}}/>
    <PhraseOptions num=8 description="My eyes hurts"  on:clicked={() => {selectPhrase(8)}}/>
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