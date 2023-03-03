<script>
	import { Button, Dropdown, DropdownItem, Chevron } from 'flowbite-svelte';
	const navs = [
		{
			title: 'ToDo',
			link: 'todo',
			child: []
		},
		{
			title: '사진첩',
			link: 'gallery',
			child: [
				{
					title: '사진첩',
					link: 'gallery'
				}
			]
		},
		{
			title: '사진첩',
			link: 'gallery',
			child: [
				{
					title: '사진첩',
					link: 'gallery'
				}
			]
		}
	];
</script>

<nav class="bg-white border-gray-200 px-2 md:px-4 py-2.5 dark:bg-gray-900">
	<div class="flex flex-wrap items-center justify-between max-w-screen-xl mx-auto">
		<a href="https://flowbite.com" class="flex items-center">
			<img
				src="https://flowbite.com/docs/images/logo.svg"
				class="h-6 mr-3 sm:h-9"
				alt="Flowbite Logo"
			/>
			<span class="self-center text-xl font-semibold whitespace-nowrap dark:text-white"
				>Flowbite</span
			>
		</a>
		<div
			id="mega-menu"
			class="items-center justify-between hidden w-full text-sm md:flex md:w-auto md:order-1"
		>
			<ul class="flex flex-col mt-4 font-medium md:flex-row md:space-x-8 md:mt-0">
				{#each navs as nav}
					{#if !nav.child.length}
						<li>
							<a
								href="#"
								class="block py-2 pl-3 pr-4 border-b border-gray-100 hover:bg-gray-50 md:hover:bg-transparent md:border-0 md:hover:text-blue-600 md:p-0 dark:text-blue-500 md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-blue-500 md:dark:hover:bg-transparent dark:border-gray-700"
								aria-current="page">Home</a
							>
						</li>
					{:else}
						<li>
							<div
							class="flex items-center justify-between w-full py-2 pl-3 pr-4 font-medium text-gray-700 border-b border-gray-100 md:w-auto hover:bg-gray-50 md:hover:bg-transparent md:border-0 md:hover:text-blue-600 md:p-0 dark:text-gray-400 md:dark:hover:text-blue-500 dark:hover:bg-gray-700 dark:hover:text-blue-500 md:dark:hover:bg-transparent dark:border-gray-700"
							>
							{nav.title}
							<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" class="h-4 w-4 ml-2" aria-label="chevron down" fill="none" viewBox="0 0 24 24" stroke-width="2"><path d="M19.5 8.25L12 15.75L4.5 8.25" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"></path> </svg></div>
							<Dropdown>
								{#each nav.child as item}
									<DropdownItem>{item.title}</DropdownItem>
								{/each}
							</Dropdown>
						</li>
					{/if}
				{/each}
			</ul>
		</div>
	</div>
</nav>
