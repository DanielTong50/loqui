<title>Quick</title>
<h1>Quick Phrases</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import { goto } from '$app/navigation'
    import { onMount } from "svelte";
    import Exitphraseoptions from "../components/exitphraseoptions.svelte";
    let key;
    //Audio files
    let Yes = new Audio("./audio/Yes.mp3")
    let No = new Audio("./audio/No.mp3")
    let Maybe = new Audio("./audio/Maybe.mp3")
    let Sure = new Audio("./audio/Sure.mp3")
    let OfCourse = new Audio("./audio/OfCourse.mp3")
    let IKnow = new Audio("./audio/IKnow.mp3")
    let Idk = new Audio("./audio/Idk.mp3")
 

	function handleKeydown(event) {
		key = event.key;
        selectPhrase(key);
    }

    function selectPhrase(num) {
        if(num == 0){
            goto('socializing');
        }

        if(num == 1){
            Yes.play();
        }

        if(num == 2){
            No.play();
        }
        
        if(num == 3){
            Maybe.play();
        }

        if(num == 4){
            Sure.play();
        }

        if(num == 5){
            OfCourse.play();
        }

        if(num == 6){
            IKnow.play();
        }

        if(num == 7){
            Idk.play();
        }
	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <Exitphraseoptions num=0 description="Exit" on:clicked={() => {selectPhrase(0)}}/>
    <PhraseOptions num=1 description="Yes" on:clicked={() => {selectPhrase(1)}}/>
    <PhraseOptions num=2 description="No" on:clicked={() => {selectPhrase(2)}}/>
    <PhraseOptions num=3 description="Maybe" on:clicked={() => {selectPhrase(3)}}/>
    <PhraseOptions num=4 description="Sure" on:clicked={() => {selectPhrase(4)}}/>
    <PhraseOptions num=5 description="Of course" on:clicked={() => {selectPhrase(5)}}/>
    <PhraseOptions num=6 description="I know" on:clicked={() => {selectPhrase(6)}}/>
    <PhraseOptions num=7 description="I do not know" on:clicked={() => {selectPhrase(7)}}/>

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