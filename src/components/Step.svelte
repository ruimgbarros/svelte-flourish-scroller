<script>
	export let stepText;
	export let i;
	export let length;
</script>

<section class="px-4" class:last-section={i === length}>
	<div
		class="px-8 py-4 text-slate-900 max-w-2xl mx-auto drop-shadow-lg border border-slate-400 text-xl font-serif"
	>
		{@html stepText}
	</div>
</section>

<style>
	section {
		margin-bottom: 80vh;
	}
	div {
		background-color: rgba(255, 255, 255, 0.9);
	}

	.last-section {
		margin-bottom: 0px;
		padding-bottom: 40vh;
	}
</style>
