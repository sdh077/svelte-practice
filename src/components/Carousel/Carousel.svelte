<script>
	import { Carousel, CarouselTransition } from 'flowbite-svelte';
	let showThumbs = false;
	let showCaptions = false;
	export let images = []
</script>

<div>
    {#if images.length}
	    <CarouselTransition transitionType="fly" {images} loop {showCaptions} {showThumbs} duration="3000" divClass={'overflow-hidden relative h-80 rounded-lg sm:h-64 xl:h-80 2xl:h-96'}/>
    {/if}
</div>
