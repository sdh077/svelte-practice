<script>
	import Breadcrumb from '$components/Breadcrumb/Breadcrumb.svelte';
	import Carousel from '$components/Carousel/Carousel.svelte';
	import Card from '$components/Card/Card.svelte';
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
	const cards = [
		{
			name: 'aaa',
			job:'bbb',
		},
		{
			name: 'ccc',
			job:'ddd',
		}
	]
	const comps = [
		{
			component: Breadcrumb,
			props: {}
		},
		{
			component: Carousel,
			props: { images }
		},
		{
			component:Card,
			props: {cards}
		}
	];
</script>

{#each comps as com}
	<svelte:component this={com.component} {...com.props} />
{/each}
