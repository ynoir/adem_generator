<script>
	import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();

	const onChange = (event) => {
		dispatch("message", {
			text: event.target.value
		});
	};

	let count = 0;
	$: countSquared = count**2;

	let onClick = () => {
		count += 1;
	};
</script>

<div>
	<p>Input:</p>
	<input type="text" on:change={onChange}/>
	<button on:click={onClick}>
		{countSquared}
	</button>
</div>
