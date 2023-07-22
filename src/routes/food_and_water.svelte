<title>Food and Water</title>
<h1>Food and Water Phrases</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import { goto } from '$app/navigation'
    import { onMount } from "svelte";
	import Exitphraseoptions from "../components/exitphraseoptions.svelte";

    let key;
    //Audio files
    let CanIHaveWater = new Audio("./audio/CanIHaveWater.mp3")
    let CanIHaveTea = new Audio("./audio/CanIHaveTea.mp3")
    let HaveSnack = new Audio("./audio/HaveSnack.mp3")
    let HaveBreakfast = new Audio("./audio/HaveBreakfast.mp3")
    let HaveLunch = new Audio("./audio/HaveLunch.mp3")
    let HaveSomeMoreFood = new Audio("./audio/HaveSomeMoreFood.mp3")
    let MoreDrink = new Audio("./audio/MoreDrink.mp3")


	function handleKeydown(event) {
		key = event.key;
        selectPhrase(key);
    }

    function selectPhrase(num) {
        if(num == 0){
            goto('needs');
        }

        if(num == 1){
            CanIHaveWater.play();
        }

        if(num == 2){
            CanIHaveTea.play();
        }
        
        if(num == 3){
            HaveSnack.play();
        }

        if(num == 4){
            HaveBreakfast.play();
        }

        if(num == 5){
            HaveLunch.play();
        }

        if(num == 6){
            HaveSomeMoreFood.play();
        }
        if(num ==7){
            MoreDrink.play();
        }

        /*
        if(num ==8) {
            test.play();
        }
        */

	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <Exitphraseoptions num=0 description="Exit "on:clicked={() => {selectPhrase(0)}}/>
    <PhraseOptions num=1 description="Can I have some water?" on:clicked={() => {selectPhrase(1)}}/>
    <PhraseOptions num=2 description="Can I have some tea?" on:clicked={() => {selectPhrase(2)}}/>
    <PhraseOptions num=3 description="Can I have a snack?" on:clicked={() => {selectPhrase(3)}}/>
    <PhraseOptions num=4 description="Can I have breakfast?" on:clicked={() => {selectPhrase(4)}}/>
    <PhraseOptions num=5 description="Can I have lunch?" on:clicked={() => {selectPhrase(5)}}/>
    <PhraseOptions num=6 description="Can I have some more food?" on:clicked={() => {selectPhrase(6)}}/>
    <PhraseOptions num=7 description="Can I have some more of my drink?" on:clicked={() => {selectPhrase(7)}}/>
</div>

<div class = "instructions">
    <p>Press the number corresponding to the phrase option. Press 0 to return to the previous page.</p>
</div>

<style>
    .instructions {
        color: gray;
        font-style: italic;
    }
</style>