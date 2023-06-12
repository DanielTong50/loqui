<title>Severe</title>
<h1>Severe Phrases</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import { goto } from '$app/navigation'
    import { onMount } from "svelte";
    import Exitphraseoptions from "../components/exitphraseoptions.svelte";

    let key;
    //Audio files
    let SevereHeadPain = new Audio("./audio/SevereHeadPain.m4a")
    let SevereArmPain = new Audio("./audio/SevereArmPain.m4a")
    let SevereBackPain = new Audio("./audio/SevereBackPain.m4a")
    let SevereLegPain = new Audio("./audio/SevereLegPain.m4a")
    let DifficultToBreathe = new Audio("./audio/DifficultToBreathe.m4a")
    let SevereChestPain = new Audio("./audio/SevereChestPain.m4a")
    let SevereEyePain = new Audio("./audio/SevereEyePain.m4a")
    let SevereFootPain = new Audio("./audio/SevereFootPain.m4a")


	function handleKeydown(event) {
		key = event.key;
        selectPhrase(key);
    }

    function selectPhrase(num) {
        if(num == 0){
            goto('emergency');
        }

        if(num == 1){
            SevereHeadPain.play();
        }

        if(num == 2){
            SevereArmPain.play();
        }
        
        if(num == 3){
            SevereBackPain.play();
        }

        if(num == 4){
            SevereLegPain.play();
        }

        if(num == 5){
            DifficultToBreathe.play();
        }

        if(num == 6){
            SevereChestPain.play();
        }

        if(num == 7){
            SevereEyePain.play();
        }

        if(num == 8){
            SevereFootPain.play();
        }

	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <Exitphraseoptions num=0 description="Exit"on:clicked={() => {selectPhrase(0)}}/>
    <PhraseOptions num=1 description="I have severe pain in my head" on:clicked={() => {selectPhrase(1)}}/>
    <PhraseOptions num=3 description="I have severe pain in my arm" on:clicked={() => {selectPhrase(2)}}/>
    <PhraseOptions num=4 description="I have severe pain in my back" on:clicked={() => {selectPhrase(3)}}/>
    <PhraseOptions num=5 description="I have severe pain in my leg" on:clicked={() => {selectPhrase(4)}}/>
    <PhraseOptions num=6 description="It is difficult to breath" on:clicked={() => {selectPhrase(5)}}/>
    <PhraseOptions num=7 description="I have severe pain in my chest" on:clicked={() => {selectPhrase(6)}}/>
    <PhraseOptions num=8 description="I have severe pain in my eyes" on:clicked={() => {selectPhrase(7)}}/>
    <PhraseOptions num=9 description="I have severe pain in my feet" on:clicked={() => {selectPhrase(8)}}/>
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