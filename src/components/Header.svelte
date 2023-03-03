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

<nav class="navbar navbar-expand-lg navbar-light">
	<div class="container position-relative">
		<a class="navbar-brand" href="/">
			Svelte Project
		</a>
		<div class="collapse navbar-collapse" id="mainNavbarTheme">
			<ul class="navbar-nav ms-auto">
				{#each navs as nav}
					<li class="nav-item dropdown">
						{#if nav.child.length}
							<a
								class="nav-link dropdown-toggle "
								href={nav.link}
								role="button"
								data-bs-toggle="dropdown"
								aria-haspopup="true"
								aria-expanded="false"
								>{nav.title}
							</a>
							<div class="dropdown-menu dropdown-menu-md dropdown-menu-start py-0 pe-lg-0">
								<div class="overflow-hidden rounded-end">
									<div class="row mx-0">
										<div class="col-lg-5 position-relative">
											<div class="py-1 py-lg-3 d-lg-flex flex-column">
												{#each nav.child as item}
													<a href={item.link} class="dropdown-item">{item.title}</a>
												{/each}
											</div>
										</div>
									</div>
								</div>
							</div>
						{:else}
							<a class="nav-link" href={nav.link} role="button">{nav.title} </a>
						{/if}
					</li>
				{/each}
			</ul>
		</div>
	</div>
</nav>
