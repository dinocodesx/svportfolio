<script lang="ts">
	let isMenuOpen = false;

	const navItems = [
		{ href: '#about', label: 'About' },
		{ href: '#skills', label: 'Skills' },
		{ href: '#experience', label: 'Experience' },
		{ href: '#projects', label: 'Projects' },
		{ href: '#volunteering', label: 'Volunteering' },
		{ href: '#blogs', label: 'Blogs' },
		{ href: '#links', label: 'Connect' }
	];

	function scrollToSection(href: string) {
		isMenuOpen = false;
		const element = document.querySelector(href);
		if (element) {
			element.scrollIntoView({ behavior: 'smooth' });
		}
	}
</script>

<header
	class="fixed top-0 right-0 left-0 z-50 border-b border-gray-800 bg-black/90 backdrop-blur-sm"
>
	<nav class="mx-auto max-w-7xl px-8 lg:px-20">
		<div class="flex h-16 items-center justify-between">
			<!-- Logo -->
			<div class="flex items-center">
				<span class="text-xl font-bold text-white">Portfolio</span>
			</div>

			<!-- Desktop Navigation -->
			<div class="hidden items-center space-x-8 md:flex">
				{#each navItems as item}
					<button
						on:click={() => scrollToSection(item.href)}
						class="text-sm font-medium text-gray-400 transition-colors hover:text-white"
					>
						{item.label}
					</button>
				{/each}
			</div>

			<!-- Mobile Menu Button -->
			<button class="text-white md:hidden" on:click={() => (isMenuOpen = !isMenuOpen)}>
				<svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
					{#if isMenuOpen}
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M6 18L18 6M6 6l12 12"
						></path>
					{:else}
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M4 6h16M4 12h16M4 18h16"
						></path>
					{/if}
				</svg>
			</button>
		</div>

		<!-- Mobile Navigation -->
		{#if isMenuOpen}
			<div class="border-t border-gray-800 bg-black/95 md:hidden">
				<div class="space-y-1 px-2 pt-2 pb-3">
					{#each navItems as item}
						<button
							on:click={() => scrollToSection(item.href)}
							class="block w-full px-3 py-2 text-left text-gray-400 transition-colors hover:text-white"
						>
							{item.label}
						</button>
					{/each}
				</div>
			</div>
		{/if}
	</nav>
</header>
