<title>Clothes</title>
<h1>Clothes Phrases</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import { goto } from '$app/navigation'
    import { onMount } from "svelte";
    import Exitphraseoptions from "../components/exitphraseoptions.svelte";

    let key;
    //Audio files
    let ChangeClothes = new Audio("./audio/ChangeClothes.mp3")
    let ButtonShirt = new Audio("./audio/ButtonShirt.mp3")
    let BrushTeeth = new Audio("./audio/BrushTeeth.mp3")
    let FlossTeeth = new Audio("./audio/FlossTeeth.mp3")
    let Deodorant = new Audio("./audio/Deodorant.mp3")

	function handleKeydown(event) {
		key = event.key;
        selectPhrase(key);
    }

    function selectPhrase(num) {

        if(num == 0){
            goto('needs');
        }

        if(num == 1){
            ChangeClothes.play();
        }

        if(num == 2){
            ButtonShirt.play();
        }
        
        if(num == 3){
            BrushTeeth.play();
        }

        if(num == 4){
            FlossTeeth.play();
        }

        if(num == 5){
            Deodorant.play();
        }
	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <Exitphraseoptions num=0 description="Exit" on:clicked={() => {selectPhrase(0)}}/>
    <PhraseOptions num=1 description="Can you help me change my clothes?" on:clicked={() => {selectPhrase(1)}}/>
    <PhraseOptions num=2 description="Can you help me button my shirt?" on:clicked={() => {selectPhrase(2)}}/>
    <PhraseOptions num=3 description="Can you help me brush my teeth?"on:clicked={() => {selectPhrase(3)}}/>
    <PhraseOptions num=4 description="Can you help me floss my teeth?" on:clicked={() => {selectPhrase(4)}}/>
    <PhraseOptions num=5 description="Can you help me put on deodorant?" on:clicked={() => {selectPhrase(5)}}/>
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