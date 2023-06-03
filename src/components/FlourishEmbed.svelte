<script>
	import { fade } from 'svelte/transition';
	export let flourish_id = 0;
	export let index = 0;
	let h;

	let elementWith;
	let chartheight = 400;

	$: {
		if (elementWith < 640) {
			chartheight = (3 * elementWith) / 2;
		} else if (elementWith < 700) {
			chartheight = (4 * elementWith) / 3;
		} else if (elementWith >= 900) {
			chartheight = (9 * elementWith) / 16;
		}
	}
</script>

<svelte:window bind:innerHeight={h} />
<div class="flex h-screen">
	<div class="w-full flex items-center">
		<figure class=" w-full" bind:clientWidth={elementWith} in:fade={{ duration: 1000 }}>
			<iframe
				src="https://flo.uri.sh/story/{flourish_id}/embed#slide-{index - 1}"
				title="Interactive or visual content"
				class="flourish-embed-iframe"
				frameborder="0"
				scrolling="no"
				style="width:100%;height:{h - 0.2 * h}px"
				sandbox="allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation"
			/>
			<div style="width:100%!;margin-top:4px!important;text-align:right!important;">
				<a
					class="flourish-credit"
					href="https://public.flourish.studio/story/1939447/?utm_source=embed&utm_campaign=story/1939447"
					target="_top"
					style="text-decoration:none!important"
					><img
						alt="Made with Flourish"
						src="https://public.flourish.studio/resources/made_with_flourish.svg"
						style="width:105px!important;height:16px!important;border:none!important;margin:0!important;"
					/>
				</a>
			</div>
		</figure>
	</div>
</div>
