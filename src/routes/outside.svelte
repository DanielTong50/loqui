<h1>Outside Phrases</h1>
<script>
    import PhraseOptions from "../components/PhraseOptions.svelte";
    import { goto } from '$app/navigation';

    let key;
	function handleKeydown(event) {
		key = event.key;
        if(key == 0){
            goto('home');
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
    <p>Press the number corresponding to the phrase. Press 0 to always return to the home page.</p>
</div>

<style>
    .instructions {
        color: gray;
        font-family: "Inter";
        font-style: italic;
    }
</style>