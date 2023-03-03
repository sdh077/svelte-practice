<script>
	import { Carousel, CarouselTransition } from 'flowbite-svelte';
	let showThumbs = false;
	let showCaptions = false;
	const images = [
		{
			id: 0,
			name: 'Cosmic timetraveler',
			imgurl: '/src/lib/carousel/1.webp',
			attribution: 'cosmic-timetraveler-pYyOZ8q7AII-unsplash.com'
		},
		{
			id: 1,
			name: 'Cristina Gottardi',
			imgurl: '/src/lib/carousel/1.jpg',
			attribution: 'cristina-gottardi-CSpjU6hYo_0-unsplash.com'
		}
	];
</script>

<div>
	<Carousel {images} loop {showCaptions} {showThumbs} duration="3000" divClass={'overflow-hidden relative h-80 rounded-lg sm:h-64 xl:h-80 2xl:h-96'}/>
</div>
