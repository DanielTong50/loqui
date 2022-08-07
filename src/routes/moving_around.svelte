<h1>Moving Around Phrases</h1>
<script>
    import Logo from "../components/Logo.svelte";
    import PhraseOptions from "../components/PhraseOptions.svelte";
    import { goto } from '$app/navigation';

    let key;
	function handleKeydown(event) {
		key = event.key;
        if(key == 0){
            goto('home');
        }
	}

</script>
<svelte:window on:keydown={handleKeydown} />
