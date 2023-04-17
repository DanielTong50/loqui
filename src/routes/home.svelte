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
            goto('/needs')
        }
        else if(num == 2){
            goto('/emergency')
        }

        else if(num == 3){
            goto('/socializing')
        }   
        
	}

</script>

<svelte:window on:keydown={handleKeydown} />
<Logo />
<div class="phrases">
    <PhraseOptions num=1 description="Needs" on:clicked={() => {selectPhrase(1)}}/>
    <PhraseOptions num=2 description="Emergency" on:clicked={() => {selectPhrase(2)}}/>
    <PhraseOptions num=3 description="Socializing" on:clicked={() => {selectPhrase(3)}}/>
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


