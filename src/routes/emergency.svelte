<h1>Emergency Phrases</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
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
        font-family: "Inter";
        font-style: italic;
    }
</style>