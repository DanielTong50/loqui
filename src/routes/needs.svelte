<title>Needs Category</title>
<h1>Needs Category</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import CategoryOptions from "../components/categoryoptions.svelte"
    import { goto } from '$app/navigation'
    import { onMount } from "svelte";
    import Exitphraseoptions from "../components/exitphraseoptions.svelte";
    let key;
    //Audio Files, however category has no audio files

    function handleKeydown(event){
        key = event.key;
        selectPhrase(key);
    }

	function selectPhrase(num) {
        if(num == 0){
            goto('/home');
        }

        else if(num == 1){
            goto('/mobility');
        }

        else if(num == 2){
            goto('/food_and_water');
        }
        else if(num == 3){
            goto('/entertainment');
        }
        else if(num == 4){
            goto('/clothes');
        }
        else if(num == 5){
            goto('/friendships');
        }
        else if(num == 6){
            goto('/temperature');
        }
	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <Exitphraseoptions num=0 description="Exit" on:clicked={() => {selectPhrase(0)}}/>
    <CategoryOptions num=1 description="Mobility" img = "mobility.png" on:clicked={() => {selectPhrase(1)}}/>
    <CategoryOptions num=2 description="Food and Water" img = "food&water.png" on:clicked={() => {selectPhrase(2)}}/>
    <CategoryOptions num=3 description="Entertainment" img = "entertainment.png" on:clicked={() => {selectPhrase(3)}}/>
    <CategoryOptions num=4 description="Clothes"img = "clothes.png" on:clicked={() => {selectPhrase(4)}}/>
    <CategoryOptions num=5 description="Friendships" img = "friends.png" on:clicked={() => {selectPhrase(5)}}/>
    <CategoryOptions num=6 description="Temperature" img = "temperature.png" on:clicked={() => {selectPhrase(6)}}/>
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