<title>Friendships</title>
<h1>Friendships Phrases</h1>
<script>
    import PhraseOptions from "../components/phraseoptions.svelte";
    import { goto } from '$app/navigation'
    import { onMount } from "svelte";
    import Exitphraseoptions from "../components/exitphraseoptions.svelte";

    let key;
    //Audio files
    let Visitors = new Audio("./audio/Visitors.m4a")
    let SeeFriends = new Audio("./audio/SeeFriends.m4a")

	function handleKeydown(event) {
		key = event.key;
        selectPhrase(key);
    }

    function selectPhrase(num) {
        if(num == 0){
            goto('needs');
        }

        if(num == 1){
            Visitors.play();
        }

        if(num == 2){
            SeeFriends.play();
        }

	}

</script>
<svelte:window on:keydown={handleKeydown} />

<div class="phrases">
    <Exitphraseoptions num=0 description="Exit" on:clicked={() => {selectPhrase(0)}}/>
    <PhraseOptions num=1 description="Do I have any visitors?" on:clicked={() => {selectPhrase(1)}}/>
    <PhraseOptions num=2 description="Can I see my friends?" on:clicked={() => {selectPhrase(2)}}/>
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