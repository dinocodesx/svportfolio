<script lang="ts">
	import { onMount } from 'svelte';

	let mounted = false;
	let showLanguageDropdown = false;

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
		// Here you would typically implement language switching logic
		console.log('Language changed to:', language.code);
	}

	function toggleLanguageDropdown() {
		showLanguageDropdown = !showLanguageDropdown;
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
	<div
		class={`bg-background fade-in pointer-events-auto relative z-50 flex h-full min-h-full items-center rounded-full px-6 shadow-lg backdrop-blur-lg ${mounted ? 'opacity-100' : 'opacity-0'}`}
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
</nav>

<style>
	.fade-in {
		transition: opacity 0.5s ease-in-out;
	}
</style>
