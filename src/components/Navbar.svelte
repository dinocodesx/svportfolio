<script lang="ts">
	import { onMount } from 'svelte';
	import { fade } from 'svelte/transition';

	let mounted = false;
	let showLanguageDropdown = false;
	let showMobileMenu = false;

	const languages = [
		{ code: 'en', name: 'English', flag: '🇺🇸' },
		{ code: 'es', name: 'Español', flag: '🇪🇸' },
		{ code: 'ja', name: '日本語', flag: '🇯🇵' },
		{ code: 'de', name: 'Deutsch', flag: '🇩🇪' },
		{ code: 'fr', name: 'Français', flag: '🇫🇷' }
	];

	let currentLanguage = languages[0];

	onMount(() => {
		mounted = true;
	});

	function selectLanguage(language: (typeof languages)[0]) {
		currentLanguage = language;
		showLanguageDropdown = false;
		showMobileMenu = false;
		// Here you would typically implement language switching logic
		console.log('Language changed to:', language.code);
	}

	function toggleLanguageDropdown() {
		showLanguageDropdown = !showLanguageDropdown;
	}

	function toggleMobileMenu() {
		showMobileMenu = !showMobileMenu;
		showLanguageDropdown = false;
	}

	function closeMobileMenu() {
		showMobileMenu = false;
		showLanguageDropdown = false;
	}

	// Close dropdown when clicking outside
	function handleClickOutside(event: MouseEvent) {
		const target = event.target as Element;
		if (!target.closest('.language-dropdown')) {
			showLanguageDropdown = false;
		}
	}

	onMount(() => {
		document.addEventListener('click', handleClickOutside);
		return () => {
			document.removeEventListener('click', handleClickOutside);
		};
	});
</script>

<nav class="pointer-events-none fixed top-4 right-4 z-30 flex h-full max-h-14 origin-top">
	<!-- Desktop Navigation -->
	<div
		class={`bg-background fade-in pointer-events-auto relative z-50 hidden h-full min-h-full items-center rounded-full px-6 shadow-lg backdrop-blur-lg md:flex ${mounted ? 'opacity-100' : 'opacity-0'}`}
		style="animation-delay: 0.5s;"
	>
		<!-- Logo/Home -->
		<a
			href="/"
			class="hover:bg-muted group relative flex items-center justify-center rounded-full px-4 py-2 text-sm font-medium transition-colors"
			title="Home"
		>
			Portfolio
		</a>

		<!-- Navigation Links -->
		<div class="ml-2 flex items-center space-x-1">
			<!-- Blogs -->
			<a
				href="/blogs"
				class="hover:bg-muted group relative flex items-center justify-center rounded-full px-4 py-2 text-sm transition-colors"
				title="Blogs"
			>
				Blogs
			</a>

			<!-- Projects -->
			<a
				href="/projects"
				class="hover:bg-muted group relative flex items-center justify-center rounded-full px-4 py-2 text-sm transition-colors"
				title="Projects"
			>
				Projects
			</a>

			<!-- Language Dropdown -->
			<div class="language-dropdown relative">
				<button
					on:click={toggleLanguageDropdown}
					class="hover:bg-muted group relative flex items-center justify-center rounded-full px-4 py-2 text-sm transition-colors"
					title="Change Language"
					aria-haspopup="true"
					aria-expanded={showLanguageDropdown}
				>
					<span class="mr-2">{currentLanguage.flag}</span>
					<span class="mr-2">{currentLanguage.name}</span>
					<svg
						class="h-4 w-4 fill-current transition-transform {showLanguageDropdown
							? 'rotate-180'
							: ''}"
						viewBox="0 0 24 24"
					>
						<path d="M7 10l5 5 5-5z" />
					</svg>
				</button>

				{#if showLanguageDropdown}
					<div
						class="bg-background border-border absolute top-full left-0 z-50 mt-2 min-w-[150px] rounded-lg border py-2 shadow-lg"
						role="menu"
						aria-orientation="vertical"
					>
						{#each languages as language}
							<button
								on:click={() => selectLanguage(language)}
								class="hover:bg-muted flex w-full items-center px-4 py-2 text-left text-sm transition-colors"
								role="menuitem"
								class:bg-muted={currentLanguage.code === language.code}
							>
								<span class="mr-3">{language.flag}</span>
								<span>{language.name}</span>
							</button>
						{/each}
					</div>
				{/if}
			</div>

			<!-- Links -->
			<a
				href="/links"
				class="hover:bg-muted group relative flex items-center justify-center rounded-full px-4 py-2 text-sm transition-colors"
				title="Links"
			>
				Links
			</a>
		</div>
	</div>

	<!-- Mobile Hamburger Button -->
	<button
		on:click={toggleMobileMenu}
		class={`bg-background fade-in hover:bg-muted pointer-events-auto relative z-50 flex h-12 w-12 items-center justify-center rounded-full shadow-lg backdrop-blur-lg transition-colors md:hidden ${mounted ? 'opacity-100' : 'opacity-0'}`}
		style="animation-delay: 0.5s;"
		aria-label="Toggle menu"
	>
		<svg
			class="h-6 w-6 fill-current transition-transform {showMobileMenu ? 'rotate-90' : ''}"
			viewBox="0 0 24 24"
		>
			{#if showMobileMenu}
				<path
					d="M19 6.41L17.59 5 12 10.59 6.41 5 5 6.41 10.59 12 5 17.59 6.41 19 12 13.41 17.59 19 19 17.59 13.41 12z"
				/>
			{:else}
				<path d="M3 18h18v-2H3v2zm0-5h18v-2H3v2zm0-7v2h18V6H3z" />
			{/if}
		</svg>
	</button>
</nav>

<!-- Mobile Full Screen Menu -->
{#if showMobileMenu}
	<div
		class="bg-background/95 fixed inset-0 z-40 backdrop-blur-lg md:hidden"
		in:fade={{ duration: 300 }}
		out:fade={{ duration: 300 }}
	>
		<div class="flex h-full flex-col items-center justify-center space-y-8 p-6">
			<!-- Logo/Home -->
			<a
				href="/"
				on:click={closeMobileMenu}
				class="hover:text-muted-foreground text-3xl font-bold transition-colors"
			>
				Portfolio
			</a>

			<!-- Navigation Links -->
			<div class="flex flex-col items-center space-y-6">
				<!-- Blogs -->
				<a
					href="/blogs"
					on:click={closeMobileMenu}
					class="hover:text-muted-foreground text-2xl transition-colors"
				>
					Blogs
				</a>

				<!-- Projects -->
				<a
					href="/projects"
					on:click={closeMobileMenu}
					class="hover:text-muted-foreground text-2xl transition-colors"
				>
					Projects
				</a>

				<!-- Language Selection -->
				<div class="flex flex-col items-center space-y-4">
					<button
						on:click={toggleLanguageDropdown}
						class="hover:text-muted-foreground flex items-center text-2xl transition-colors"
						aria-haspopup="true"
						aria-expanded={showLanguageDropdown}
					>
						<span class="mr-3">{currentLanguage.flag}</span>
						<span class="mr-2">{currentLanguage.name}</span>
						<svg
							class="h-6 w-6 fill-current transition-transform {showLanguageDropdown
								? 'rotate-180'
								: ''}"
							viewBox="0 0 24 24"
						>
							<path d="M7 10l5 5 5-5z" />
						</svg>
					</button>

					{#if showLanguageDropdown}
						<div class="flex flex-col items-center space-y-3">
							{#each languages as language}
								<button
									on:click={() => selectLanguage(language)}
									class="hover:text-muted-foreground flex items-center text-lg transition-colors"
									class:text-muted-foreground={currentLanguage.code === language.code}
								>
									<span class="mr-3">{language.flag}</span>
									<span>{language.name}</span>
								</button>
							{/each}
						</div>
					{/if}
				</div>

				<!-- Links -->
				<a
					href="/links"
					on:click={closeMobileMenu}
					class="hover:text-muted-foreground text-2xl transition-colors"
				>
					Links
				</a>
			</div>
		</div>
	</div>
{/if}

<style>
	.fade-in {
		transition: opacity 0.5s ease-in-out;
	}
</style>
