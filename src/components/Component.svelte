<script>
	import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();

	let text = "";
	$: {
		dispatch("message", {
			text: text
		});
	}

	let count = 0;
	$: countSquared = count**2;

	let onClick = () => {
		count += 1;
	};
</script>

<div>
	<p>Input:</p>
	<input type="text" bind:value={text}/>
	<button on:click={onClick}>
		{countSquared}
	</button>
</div>
