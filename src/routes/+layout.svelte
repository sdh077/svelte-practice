<script>
	import '../app.postcss';
	// import '../app.css';
	import '../font.css';
	import Header from '$components/Header2.svelte';
	import 'flowbite/dist/flowbite.css';
</script>

<header />

<div class="w-full px-4 mx-auto max-w-8xl">
	<slot>
		this fallback content will be rendered when no content is provided, like in the first example
	</slot>
</div>
