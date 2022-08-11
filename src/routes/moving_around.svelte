<title>Moving Around</title>
<h1>Moving Around Phrases</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import { goto } from '$app/navigation';

    let key;

    let thanks = new Audio("./Audio_files/Thanks.mp3")
    let sorry = new Audio("./Audio_files/Sorry.mp3")
    let excuseme = new Audio("./Audio_files/ExcuseMe.mp3")
    let hello = new Audio("./Audio_files/Hello.mp3")
    let helpmewiththis = new Audio("./Audio_files/HelpMeWithThis.mp3")
    let hungry = new Audio("./Audio_files/Hungry.mp3")

	function handleKeydown(event) {
		key = event.key;
        if(key == 0){
            goto('home');
        }

        if (key == 1){
            thanks.play();
        }

        if (key == 2){
            sorry.play();
        }

        if (key == 3){
            excuseme.play();
        }

        if (key == 4){
            hello.play();
        }

        if (key == 5){
            helpmewiththis.play();
        }

        if (key == 6){
            hungry.play();
        }
	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <PhraseOptions num=0 description="Exit"/>
    <PhraseOptions num=1 description="Thanks."/>
    <PhraseOptions num=2 description="Sorry."/>
    <PhraseOptions num=3 description="Excuse me."/>
    <PhraseOptions num=4 description="Hello!"/>
    <PhraseOptions num=5 description="Could you help me with this please?"/>
    <PhraseOptions num=6 description="I'm hungry."/>
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