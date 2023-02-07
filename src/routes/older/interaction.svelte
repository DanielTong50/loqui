<title>Interaction</title>
<h1>Interaction Phrases</h1>
<script>
    import PhraseOptions from "../../components/phraseoptions.svelte";
    import { goto } from '$app/navigation';

    let key;

    let speakup = new Audio("./Audio_files/SpeakUp.mp3")
    let nicetomeet = new Audio("./Audio_files/NiceToMeet.mp3")
    let name = new Audio("./Audio_files/YourName.mp3")
    let work = new Audio("./Audio_files/DoForWork.mp3")

	function handleKeydown(event) {
		key = event.key;
        if(key == 0){
            goto('home');
        }

        if (key == 1){
            speakup.play();
        }

        if (key == 2){
            nicetomeet.play();
        }

        if (key == 3){
            name.play();
        }

        if (key == 4){
            work.play();
        }
	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <PhraseOptions num=0 description="Exit"/>
    <PhraseOptions num=1 description="Sorry I can’t hear you, can you speak up a little bit
    ."/>
    <PhraseOptions num=2 description="Nice to meet you."/>
    <PhraseOptions num=3 description="What is your name?"/>
    <PhraseOptions num=4 description="What do you do for work?"/>

</div>

<div class = "instructions">
    <p>Press the number corresponding to the phrase. Press 0 to always return to the home page.</p>
</div>

<style>
    .instructions {
        color: gray;
        font-family: "Inter";
        font-style: italic;
    }
</style>