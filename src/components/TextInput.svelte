<script>
	import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();
	export let text = "";
	export let fontsize = "";
</script>

<div>
	<p>text:</p>
	<input type="text" bind:value={text}/>
	<p>font size:</p>
	<input type="text" bind:value={fontsize}/>
</div>
