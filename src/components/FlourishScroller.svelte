<script>
	import Scroller from '@sveltejs/svelte-scroller';
	import FlourishEmbed from './FlourishEmbed.svelte';
	import Step from './Step.svelte';

	export let flourish_id = 0;
	export let steps;
	let length = steps.length - 1;

	let offset, progress;
	let index = 0;
	let top = 0.1;
	let threshold = 0.9;
	let bottom = 0.9;
</script>

<main class="max-w-6xl mx-auto">
	<Scroller top={0} bottom={0.9} bind:index bind:offset bind:progress {threshold}>
		<div slot="background" class="px-4">
			<FlourishEmbed {flourish_id} {index} />
		</div>

		<div slot="foreground" id="steps">
			<div class="fadein">
				<section />
				{#each steps as stepText, i}
					<Step {stepText} {length} {i} />
				{/each}
			</div>
		</div>
	</Scroller>
</main>

<style>
	section {
		height: 80vh;
	}

	.fadein {
		animation: fadeIn ease 2s;
		-webkit-animation: fadeIn ease 2s;
		-moz-animation: fadeIn ease 2s;
		-o-animation: fadeIn ease 2s;
		-ms-animation: fadeIn ease 2s;
	}

	@keyframes fadeIn {
		0% {
			opacity: 0;
		}
		100% {
			opacity: 1;
		}
	}

	[slot='foreground'] {
		pointer-events: none;
	}

	/* [slot='foreground'] section {
		pointer-events: all;
	} */
</style>
