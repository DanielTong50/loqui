<title>Emergency</title>
<h1>Emergency Phrases</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import { goto } from '$app/navigation';

    let key;

    let headhurts = new Audio("./Audio_files/HeadHurts.mp3")
    let neckhurts = new Audio("./Audio_files/NeckHurts.mp3")
    let backhurts = new Audio("./Audio_files/BackPain.mp3")
    let armhurts = new Audio("./Audio_files/ArmPain.mp3")
    let legshurt = new Audio("./Audio_files/LegPain.mp3")
    let chesthurt = new Audio("./Audio_files/ChestPain.mp3")


	function handleKeydown(event) {
		key = event.key;
        if(key == 0){
            goto('home');
        }

        if (key == 1){
            headhurts.play();
        }

        if (key == 2){
            neckhurts.play();
        }

        if (key == 3){
            backhurts.play();
        }

        if (key == 4){
            armhurts.play();
        }

        if (key == 5){
            legshurt.play();
        }

        if (key == 6){
            chesthurt.play();
        }
	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <PhraseOptions num=0 description="Exit"/>
    <PhraseOptions num=1 description="Pain in Head"/>
    <PhraseOptions num=2 description="Pain in Neck"/>
    <PhraseOptions num=3 description="Pain in Back"/>
    <PhraseOptions num=4 description="Pain in Arms"/>
    <PhraseOptions num=5 description="Pain in Legs"/>
    <PhraseOptions num=6 description="Pain in Chest"/>
</div>

<div class = "instructions">
    <p>Press the number corresponding to the phrase. Press 0 to always return to the home page.</p>
</div>

<style>
    .instructions {
        color: gray;
        font-family: "Inter", sans-serif;
        font-style: italic;
    }
</style>