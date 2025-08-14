<script lang="ts">
	import { onMount } from 'svelte';

	let mounted = false;

	const socialLinks = [
		{
			href: 'https://github.com/debarshee2004',
			icon: 'M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z',
			label: 'GitHub'
		},
		{
			href: 'https://linkedin.com/in/debarsheedas2004',
			icon: 'M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z',
			label: 'LinkedIn'
		},
		{
			href: 'https://twitter.com/debarshee2004',
			icon: 'M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z',
			label: 'Twitter'
		},
		{
			href: 'mailto:debarsheedas2004@gmail.com',
			icon: 'M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 0 1 0 19.366V5.457c0-.904.732-1.636 1.636-1.636h3.819v.001L12 8.773l6.545-4.951h3.819C23.268 3.821 24 4.553 24 5.457z',
			label: 'Email'
		}
	];

	onMount(() => {
		mounted = true;
	});
</script>

<div
	class="pointer-events-none fixed inset-x-0 bottom-0 z-30 mx-auto mb-4 flex h-full max-h-14 origin-bottom"
>
	<div
		class="bg-background fixed inset-x-0 bottom-0 h-16 w-full to-transparent backdrop-blur-lg"
	></div>
	<div
		class={`bg-background border-border fade-in pointer-events-auto relative z-50 mx-auto flex h-full min-h-full items-center rounded-full border px-1 shadow-lg ${mounted ? 'opacity-100' : 'opacity-0'}`}
		style="animation-delay: 2s;"
	>
		<!-- Blog link -->
		<a
			href="/blogs"
			class="hover:bg-muted group relative flex size-12 items-center justify-center rounded-full transition-colors"
			title="Blog"
		>
			<svg class="h-4 w-4 fill-current" viewBox="0 0 24 24">
				<path
					d="M4 19.5A2.5 2.5 0 0 1 1.5 17V7A2.5 2.5 0 0 1 4 4.5h16A2.5 2.5 0 0 1 22.5 7v10a2.5 2.5 0 0 1-2.5 2.5H4zm0-1.5h16a1 1 0 0 0 1-1V7a1 1 0 0 0-1-1H4a1 1 0 0 0-1 1v10a1 1 0 0 0 1 1zm1-9h14v1H5v-1zm0 3h14v1H5v-1zm0 3h10v1H5v-1z"
				/>
			</svg>
			<div
				class="bg-foreground text-background pointer-events-none absolute bottom-full mb-2 rounded px-2 py-1 text-xs whitespace-nowrap opacity-0 transition-opacity group-hover:opacity-100"
			>
				Blog
			</div>
		</a>

		<!-- Links page -->
		<a
			href="/links"
			class="hover:bg-muted group relative flex size-12 items-center justify-center rounded-full transition-colors"
			title="Links"
		>
			<svg class="h-4 w-4 fill-current" viewBox="0 0 24 24">
				<path
					d="M10.59 13.41c.41.39.41 1.03 0 1.42-.39.39-1.03.39-1.42 0a5.003 5.003 0 0 1 0-7.07l3.54-3.54a5.003 5.003 0 0 1 7.07 0 5.003 5.003 0 0 1 0 7.07l-1.49 1.49c.01-.82-.12-1.64-.4-2.42l.47-.48a2.982 2.982 0 0 0 0-4.24 2.982 2.982 0 0 0-4.24 0l-3.53 3.53a2.982 2.982 0 0 0 0 4.24zm2.82-4.24c.39-.39 1.03-.39 1.42 0a5.003 5.003 0 0 1 0 7.07l-3.54 3.54a5.003 5.003 0 0 1-7.07 0 5.003 5.003 0 0 1 0-7.07l1.49-1.49c-.01.82.12 1.64.4 2.43l-.47.47a2.982 2.982 0 0 0 0 4.24 2.982 2.982 0 0 0 4.24 0l3.53-3.53a2.982 2.982 0 0 0 0-4.24.996.996 0 0 1 0-1.42z"
				/>
			</svg>
			<div
				class="bg-foreground text-background pointer-events-none absolute bottom-full mb-2 rounded px-2 py-1 text-xs whitespace-nowrap opacity-0 transition-opacity group-hover:opacity-100"
			>
				Links
			</div>
		</a>

		<!-- Separator -->
		<div class="bg-border mx-1 h-8 w-px"></div>

		<!-- Social links -->
		{#each socialLinks as social}
			<a
				href={social.href}
				target="_blank"
				rel="noopener noreferrer"
				class="hover:bg-muted group relative flex size-12 items-center justify-center rounded-full transition-colors"
				title={social.label}
			>
				<svg class="h-4 w-4 fill-current" viewBox="0 0 24 24">
					<path d={social.icon} />
				</svg>
				<div
					class="bg-foreground text-background pointer-events-none absolute bottom-full mb-2 rounded px-2 py-1 text-xs whitespace-nowrap opacity-0 transition-opacity group-hover:opacity-100"
				>
					{social.label}
				</div>
			</a>
		{/each}
	</div>
</div>
