<script>
	import Component from "./components/Component.svelte";
	import Out from "./components/Out.svelte";
	export let name;
	const onMessage = (event) => {
		name = event.detail.text;
	};
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<Component on:message={onMessage}/>
	<Out text={"some text"}/>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}
	p {
		color: green;
	}
	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>