<script>
	import TextInput from "./components/TextInput.svelte";
	import domtoimage from "dom-to-image";
	import FileSaver from "file-saver";

	export let text = "grateful";
	export let fontsize = 1.4;

	const save = () => {
		domtoimage.toBlob(document.getElementById("adem"))
			.then(function (blob) {
				FileSaver.saveAs(blob, "adem_" + text + ".png");
			});
	};
</script>

<main>
	<div id="adem" class="icon">
		<img alt="adem face" src="/adem_face.png"/>
		<div class="text" style="font-size: {fontsize}em">{text}</div>
	</div>
	<TextInput bind:text={text} bind:fontsize={fontsize}/>
	<button on:click={save}>save</button>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	.icon {
		padding-top: 10px;
		padding-bottom: 10px;
		height: 120px;
		width: 120px;
		background-color: #911a1e;
	}

	.text {
		color: #ffffff;
		text-transform: uppercase;
		font-weight: 800;
	}

</style>
