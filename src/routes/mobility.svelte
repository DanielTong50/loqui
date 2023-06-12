<title>Mobility</title>
<h1>Mobility Phrases</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import { goto } from '$app/navigation'
    import { onMount } from "svelte";
    import Exitphraseoptions from "../components/exitphraseoptions.svelte";
    let key;
    //Audio files
    let HelpToTheRestroom = new Audio("./audio/HelpToTheRestroom.m4a")
    let HelpToTheDiningRoom = new Audio("./audio/HelpToTheDiningRoom.m4a")
    let GoOutside = new Audio("./audio/GoOutside.m4a")
    let HelpToMyRoom = new Audio("./audio/HelpToMyRoom.m4a")
    let HelpToMyBed = new Audio("./audio/HelpToMyBed.m4a")

	function handleKeydown(event) {
		key = event.key;
        selectPhrase(key);
    }

    function selectPhrase(num) {
        if(num == 0){
            goto('/needs');
        }

        else if(num == 1){
            HelpToTheRestroom.play();
        }

        else if(num == 2){
            HelpToTheDiningRoom.play();
        }
        
        else if(num == 3){
            GoOutside.play();
        }

        else if(num == 4){
            HelpToMyRoom.play();
        }

        else if(num == 5){
            HelpToMyBed.play();
        }

	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <Exitphraseoptions num=0 description="Exit" on:clicked={() => {selectPhrase(0)}}/>
    <PhraseOptions num=1 description="Can you help me get to the restroom?" on:clicked={() => {selectPhrase(1)}} />
    <PhraseOptions num=2 description="Can you help me get to the dining room?" on:clicked={() => {selectPhrase(2)}}/>
    <PhraseOptions num=3 description="Can I go outside?" on:clicked={() => {selectPhrase(3)}}/>
    <PhraseOptions num=4 description="Can you help me get to my room?" on:clicked={() => {selectPhrase(4)}}/>
    <PhraseOptions num=5 description="Can you help me get to my bed?" on:clicked={() => {selectPhrase(5)}}/>
</div>

<div class = "instructions">
    <p>Press the number corresponding to the phrase option. Press 0 anytime to return to the previous page.</p>
</div>

<style>
    .instructions {
        color: gray;
        font-style: italic;
    }
</style>