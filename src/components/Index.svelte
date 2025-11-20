<script>
	import useWindowDimensions from "$runes/useWindowDimensions.svelte";

	let dimensions = new useWindowDimensions();
	let svhEl = $state(null);
	let svh = $derived(dimensions.height && svhEl ? svhEl.clientHeight : 0);
</script>

<section>
	<!-- <div
		class="fixed"
		style:width={dimensions.width + "px"}
		style:height={dimensions.height + "px"}
	>
		<p>{dimensions.width} x {dimensions.height}</p>
	</div> -->
	<div class="svh" bind:this={svhEl}>
		<p>svh: {svh}</p>
	</div>
</section>

<div class="spacer"></div>
<div class="spacer"></div>
<div class="spacer"></div>
<div class="spacer"></div>

<style>
	section {
		overflow: hidden;
	}

	div.fixed {
		position: fixed;
		top: 0;
		left: 0;
		background: lightpink;
		border: 2px solid red;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	p {
		margin: 0;
		text-align: center;
	}

	div.svh {
		width: 100%;
		height: 100svh;
		background: lightgreen;
		display: flex;
		justify-content: center;
		align-items: center;
		border: 2px solid green;
		position: fixed;
		top: 0;
		left: 0;
	}
	div.spacer {
		height: 600px;
		background: lightblue;
	}
</style>
