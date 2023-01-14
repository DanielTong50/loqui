<title>Loqui</title>
<script>
    import Logo from "../components/logo.svelte";
    import PhraseOptions from "../components/phraseoptions.svelte";
    import { goto } from '$app/navigation';

    let key;

    function handleKeydown(event){
        key = event.key;
        selectPhrase(key);
    }

	function selectPhrase(num) {	
        if(num == 1){
            goto('/general')
        }
        else if(num == 2){
            goto('/outside')
        }

        else if(num == 3){
            goto('/moving_around')
        }

        else if(num == 4){
            goto('/emergency')
        }
		
        else if(num == 5){
            goto('interaction')
        }

	}

</script>

<svelte:window on:keydown={handleKeydown} />
<Logo />
<div class="phrases">
    <PhraseOptions num=1 description="General" on:clicked={() => {selectPhrase(1)}}/>
    <PhraseOptions num=2 description="Outside" on:clicked={() => {selectPhrase(2)}}/>
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


