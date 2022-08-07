<script>
    import Logo from "../components/Logo.svelte";
    import PhraseOptions from "../components/PhraseOptions.svelte";
    import { goto } from '$app/navigation';

    let key;
	function handleKeydown(event) {
		key = event.key;
        if(key == 1){
            goto('/general')
        }
        else if(key == 2){
            goto('/')
        }
		
	}

</script>

<svelte:window on:keydown={handleKeydown} />
<Logo />
<div class="phrases">
    <PhraseOptions num=1 description="General"/>
    <PhraseOptions num=2 description="At Home"/>
    <PhraseOptions num=3 description="Outside"/>
    <PhraseOptions num=4 description="Moving Around"/>
    <PhraseOptions num=5 description="Emergency"/>
    <PhraseOptions num=6 description="Interaction"/>
</div>

<div class = "instructions">
    <p>Press the number corresponding to the phrase option. Press 0 to always return to the home page.</p>
</div>

<style>
    .instructions {
        color: gray;
        font-family: "Inter";
        font-style: italic;
    }
</style>


