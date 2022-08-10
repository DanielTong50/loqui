<h1>Moving Around Phrases</h1>
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