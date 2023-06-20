<title>Socializing Category</title>
<h1>Socializing Category</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import CategoryOptions from "../components/categoryoptions.svelte"
    import { goto } from '$app/navigation'
    import { onMount } from "svelte";
    import Exitphraseoptions from "../components/exitphraseoptions.svelte";
    let key;
    //Audio files

	function handleKeydown(event) {
		key = event.key;
        selectPhrase(key);
    }

    function selectPhrase(num) {
        if(num == 0){
            goto('/home');
        }

        if(num == 1){
            goto('/quick');
        }

        if(num == 2){
            goto('/thanking');
        }
        
        if(num == 3){
            goto('/routine');
        }

        if(num == 4){
            goto('/conversation');
        }
	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <Exitphraseoptions num=0 description="Exit" on:clicked={() => {selectPhrase(0)}}/>
    <PhraseOptions num=1 description="Quick" on:clicked={() => {selectPhrase(1)}}/>
    <PhraseOptions num=2 description="Thanking" on:clicked={() => {selectPhrase(2)}}/>
    <PhraseOptions num=3 description="Routine" on:clicked={() => {selectPhrase(3)}}/>
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