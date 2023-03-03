<script>
	import { Card, MenuButton, Dropdown, DropdownItem, Avatar, Button } from 'flowbite-svelte';
	export let cards = [];
</script>

<div class="flex py-4">
	{#each cards as card}
		<Card padding="sm" class="mx-3">
			<div class="flex justify-end">
				<MenuButton />
				<Dropdown class="w-36">
					<DropdownItem>Edit</DropdownItem>
					<DropdownItem>Export data</DropdownItem>
					<DropdownItem>Delete</DropdownItem>
				</Dropdown>
			</div>
			<div class="flex flex-col items-center pb-4">
				<Avatar size="lg" src="/src/lib/card/2.jpg" />
				<h5 class="mb-1 text-xl font-medium text-gray-900 dark:text-white">{card.name}</h5>
				<span class="text-sm text-gray-500 dark:text-gray-400">{card.job}</span>
				<div class="flex mt-4 space-x-3 lg:mt-6">
					<Button>Add friend</Button>
					<Button color="light" class="dark:text-white">Message</Button>
				</div>
			</div>
		</Card>
	{/each}
</div>
