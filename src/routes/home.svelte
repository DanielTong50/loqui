<title>Loqui</title>
<script>
   //import Logo from "../components/logo.svelte";
   import CategoryOptions from "../components/categoryoptions.svelte"; 
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

<div class="title">
    <img src = "favicon.png" alt="Logo" />
    <h1>LOQUI</h1>
    <p>Assistive Technology</p>
</div>

<div class="phrases">
    <CategoryOptions num=1 description= "Needs" img = "needs.png" on:clicked={() => {selectPhrase(1)}}/>
    <CategoryOptions num=2 description="Emergency" img = "Emergency.png" on:clicked={() => {selectPhrase(2)}}/>
    <CategoryOptions num=3 description="Socializing" img = "General.png" on:clicked={() => {selectPhrase(3)}}/>
</div>

<div class = "instructions">
    <p>Press the number corresponding to the phrase option. Press 0 anytime to return to the home page.</p>
    <p>Icons by Flaticon and The Noun Project</p>
</div>

<style>
    .instructions {
        color: gray;
        font-style: italic;
        align-items: center;
        text-align: center;
    }
    .title {
        align-items: center;
        text-align: center;
    }

    img {
        width: 100px;
        margin: 0;
    }
    
</style>



