<title>Entertainment</title>
<h1>Entertainment Phrases</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import { goto } from '$app/navigation'
    import { onMount } from "svelte";

    let key;
    //Audio files
    let WatchTV = new Audio("./audio/WatchTV.m4a")
    let PlayGame = new Audio("./audio/PlayGame.m4a")
    let UseComputer = new Audio("./audio/UseComputer.m4a")
    let ReadBook = new Audio("./audio/ReadBook.m4a")
    let TellStory = new Audio("./audio/TellStory.m4a")
    let TellJoke = new Audio("./audio/TellJoke.m4a")

	function handleKeydown(event) {
		key = event.key;
        selectPhrase(key);
    }

    function selectPhrase(num) {
        if(num == 0){
            goto('/needs');
        }

        if(num == 1){
            WatchTV.play();
        }

        if(num == 2){
            PlayGame.play();
        }
        
        if(num == 3){
            UseComputer.play();
        }

        if(num == 4){
            ReadBook.play();
        }

        if(num == 5){
            TellStory.play();
        }

        if(num == 6){
            TellJoke.play();
        }
	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <PhraseOptions num=0 description="Exit" on:clicked={() => {selectPhrase(0)}}/>
    <PhraseOptions num=1 description="Can I watch TV?" on:clicked={() => {selectPhrase(1)}}/>
    <PhraseOptions num=2 description="Can we play a game?" on:clicked={() => {selectPhrase(2)}}/>
    <PhraseOptions num=3 description="Can I use my computer?" on:clicked={() => {selectPhrase(3)}}/>
    <PhraseOptions num=4 description="Can you read me a book?" on:clicked={() => {selectPhrase(4)}}/>
    <PhraseOptions num=5 description="Can you tell me a story?" on:clicked={() => {selectPhrase(5)}}/>
    <PhraseOptions num=6 description="Can you tell me a joke?" on:clicked={() => {selectPhrase(6)}}/>
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