<script>
    import PhraseOptions from "../../components/phraseoptions.svelte";
    import { goto } from '$app/navigation'
    import { onMount } from "svelte";

    let key;
    //Audio files
    let HelpToTheRestroom = new Audio("./Audio/HelpToTheRestroom.m4a");

    function handleKeydown(event){
        key = event.key;
        selectPhrase(key);
    }


	function selectPhrase(event) {
		key = event.key;
        if(num == 0){
            goto('home');
        }

        if(num == 1){
            HelpToTheRestroom.play();
        }

        if(num == 2){
            sorry.play();
        }
        
        if(num == 3){
            excuseme.play();
        }

        if(num == 4){
            hello.play();
        }

        if(num == 5){
            helpmewiththis.play();
        }

        if(num == 6){
            hungry.play();
        }


	}

</script>
<svelte:window on:keydown={handleKeydown} />



<div class="phrases">
    <PhraseOptions num=0 description="Exit" on:clicked={() => {selectPhrase(0)}}/>
    <PhraseOptions num=1 description="Can you help me get to the restroom?"/>
    <PhraseOptions num=2 description="Can you help me get to the TV room?"/>
    <PhraseOptions num=3 description="Can you help me get to the dining room?"/>
    <PhraseOptions num=4 description="Can I go outside?"/>
    <PhraseOptions num=5 description="Can you help me get to my room?"/>
    <PhraseOptions num=6 description="Can you help me get to my bed?”"/>
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