<script>
    import Logo from "../components/logo.svelte";
    import PhraseOptions from "../components/phraseoptions.svelte";
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
    <PhraseOptions num=3 description="Moving Around"/>
    <PhraseOptions num=4 description="Emergency"/>
    <PhraseOptions num=5 description="Other"/>
</div>


