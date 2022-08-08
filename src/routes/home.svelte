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
            goto('/outside')
        }

        else if(key == 3){
            goto('/moving_around')
        }

        else if(key == 4){
            goto('/emergency')
        }
		
        else if(key == 5){
            goto('interaction')
        }

	}

</script>

<svelte:window on:keydown={handleKeydown} />
<Logo />
<div class="phrases">
    <PhraseOptions num=1 description="General"/>
    <PhraseOptions num=2 description="Outside"/>
    <PhraseOptions num=3 description="Moving Around"/>
    <PhraseOptions num=4 description="Emergency"/>
    <PhraseOptions num=5 description="Interaction"/>
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


