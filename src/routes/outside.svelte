<title>Outside</title>
<h1>Outside Phrases</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import { goto } from '$app/navigation';

    let key;

    let water = new Audio("./Audio_files/Water.mp3")
    let food = new Audio("./Audio_files/Food.mp3")
    let bus = new Audio("./Audio_files/Bus.mp3")
    let excuseme = new Audio("./Audio_files/ExcuseMe.mp3")
    let getthrough = new Audio("./Audio_files/GetThrough.mp3")
    let getthere = new Audio("./Audio_files/HelpMeGetThere.mp3")

	function handleKeydown(event) {
		key = event.key;
        if(key == 0){
            goto('home');
        }

        if (key == 1){
            water.play();
        }

        if (key == 2){
            food.play();
        }

        if (key == 3){
            bus.play();
        }

        if (key == 4){
            excuseme.play();
        }

        if (key == 5){
            getthrough.play();
        }

        if (key == 6){
            getthere.play();
        }
	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <PhraseOptions num=0 description="Exit"/>
    <PhraseOptions num=1 description="Could I get some water?"/>
    <PhraseOptions num=2 description="Could I get some food?."/>
    <PhraseOptions num=3 description="I need to get on the bus. Please lower the ramp, thanks"/>
    <PhraseOptions num=4 description="Excuse me."/>
    <PhraseOptions num=5 description="I need to get through, thanks"/>
    <PhraseOptions num=6 description="Can you help me get over there, please?"/>
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