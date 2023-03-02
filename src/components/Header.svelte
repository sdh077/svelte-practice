<script>
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
		}
	];
</script>

<nav
	class="minimum-width-rem inset-x-0 top-0 flex h-14 w-full items-center justify-center border-b bg-white px-3 shadow-md sm:h-20 sm:px-10 z-40 delay-500 svelte-1482j9b"
>
	<div class="flex w-full items-center justify-between gap-4 lg:gap-8">
		<div class="flex items-center gap-4">
			<a href="/" aria-label="Click to route home page" class="block shrink-0">Svelte Project</a>
		</div>
		<div class="hidden lg:block">
			<ul class="flex flex-row items-center justify-center font-semibold tracking-wide">
				{#each navs as nav}
					<li
						class="hoverable mx-1 svelte-bmrkxt"
						id="menu-button"
						aria-expanded="true"
						aria-haspopup="true"
					>
						{#if !nav.child.length}
							<div
								class="itmes-center relative flex h-20 shrink-0 justify-center whitespace-nowrap border-b-4 border-transparent p-2 font-medium uppercase hover:border-yellow-500           "
								id="dropdownMenuButton1"
								data-te-dropdown-toggle-ref
								aria-expanded="false"
								data-te-ripple-init
							>
								<a
									href={nav.link}
									aria-label="Click to route into category related products page"
									data-sveltekit-reload=""
									class="flex w-full items-center gap-1"
									><span>{nav.title}</span>
								</a>
							</div>
						{:else}
							<div class="dropdown">
								<span>{nav.title}</span>
								<div class="dropdown-content">
									{#each nav.child as item}
										<p><a href={item.link}>{item.title}</a></p>
									{/each}
								</div>
							</div>
						{/if}
					</li>
				{/each}
			</ul>
		</div>
	</div>
</nav>

<style>
	.dropdown {
		position: relative;
		display: inline-block;
	}

	.dropdown-content {
		display: none;
		position: absolute;
		padding: 12px 16px;
		z-index: 1;
		min-width: 160px;
		background-color: #f9f9f9;
	}

	.dropdown:hover .dropdown-content {
		display: block;
	}
</style>
