<title>Temperature</title>
<h1>Temperature Phrases</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import { goto } from '$app/navigation'
    import { onMount } from "svelte";
    import Exitphraseoptions from "../components/exitphraseoptions.svelte";

    let key;
    //Audio files
    let Temperature = new Audio("./audio/Temperature.mp3")
    let Weather = new Audio("./audio/Weather.mp3")
    let Cold = new Audio("./audio/Cold.mp3")
    let Hot = new Audio("./audio/Hot.mp3")
    let RoomColder = new Audio("./audio/RoomColder.mp3")
    let RoomHotter = new Audio("./audio/RoomHotter.mp3")

	function handleKeydown(event) {
		key = event.key;
        selectPhrase(key);
    }

    function selectPhrase(num) {
        if(num == 0){
            goto('needs');
        }

        if(num == 1){
            Temperature.play();
        }

        if(num == 2){
            Weather.play();
        }
        
        if(num == 3){
            Cold.play();
        }

        if(num == 4){
            Hot.play();
        }

        if(num == 5){
            RoomColder.play();
        }

        if(num == 6){
            RoomHotter.play();
        }

	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <Exitphraseoptions num=0 description="Exit" on:clicked={() => {selectPhrase(0)}}/>
    <PhraseOptions num=1 description="What is the temperature?" on:clicked={() => {selectPhrase(1)}}/>
    <PhraseOptions num=2 description="What is the weather today?" on:clicked={() => {selectPhrase(2)}}/>
    <PhraseOptions num=3 description="I am cold" on:clicked={() => {selectPhrase(3)}}/>
    <PhraseOptions num=4 description="I am hot" on:clicked={() => {selectPhrase(4)}}/>
    <PhraseOptions num=5 description="Can you make the room colder?" on:clicked={() => {selectPhrase(5)}}/>
    <PhraseOptions num=6 description="Can you make the room hotter?" on:clicked={() => {selectPhrase(6)}}/>
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