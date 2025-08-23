<script lang="ts">
	import { onMount } from 'svelte';

	const currentYear = new Date().getFullYear();
	let mounted = false;

	onMount(() => {
		mounted = true;
	});
</script>

<footer class="border-border relative mt-24 border-t pt-16">
	<div class="space-y-16">
		<!-- Header -->
		<div class={`${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 0.2s;">
			<div class="mb-8 flex items-center space-x-8">
				<h2 class="text-4xl font-black tracking-wider uppercase">Footer</h2>
				<div class="bg-foreground h-px flex-1"></div>
			</div>
		</div>

		<!-- Footer Content Grid -->
		<div class="grid grid-cols-1 gap-12 lg:grid-cols-12">
			<!-- Main Message -->
			<div class="lg:col-span-6">
				<div
					class={`space-y-6 ${mounted ? 'opacity-100' : 'opacity-0'}`}
					style="animation-delay: 0.3s;"
				>
					<h3 class="text-2xl font-black tracking-wide uppercase">
						Let's Build Something Amazing Together
					</h3>
					<p class="text-muted-foreground max-w-lg text-lg leading-relaxed font-light">
						I'm always interested in new opportunities and exciting projects. Let's connect and
						create something extraordinary.
					</p>
				</div>

				<h3 class="text-muted-foreground mt-6 mb-10 text-sm font-medium tracking-wider uppercase">
					Check this out
				</h3>

				<div class="space-y-4">
					<!-- Retro Version -->
					<a
						href="https://retro.dinocodes.in"
						class="group border-foreground bg-background hover:bg-foreground hover:text-background flex w-full items-center justify-between border-2 p-6 font-mono text-sm tracking-wider uppercase transition-colors duration-200"
					>
						<div class="flex items-center space-x-4">
							<div
								class="bg-foreground group-hover:bg-background flex h-8 w-8 items-center justify-center"
							>
								<span class="text-background group-hover:text-foreground text-xs font-black"
									>建築</span
								>
							</div>
							<span>Retro Vibes</span>
						</div>
						<div class="text-muted-foreground group-hover:text-background/70 text-xs">→</div>
					</a>
				</div>
			</div>

			<!-- Links & Info -->
			<div class="lg:col-span-6">
				<div class="grid grid-cols-1 gap-8 md:grid-cols-2">
					<!-- Quick Links -->
					<div class={`${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 0.4s;">
						<div class="border-foreground border-l-4 pl-6">
							<h4 class="text-muted-foreground mb-4 text-sm font-medium tracking-wider uppercase">
								Quick Links
							</h4>
							<div class="space-y-3">
								<a
									target="_blank"
									href="https://github.com/debarshee2004"
									class="hover:text-muted-foreground group flex items-center space-x-3 text-sm font-medium transition-colors"
								>
									<div class="bg-foreground h-px transition-all group-hover:w-2"></div>
									<span>Projects</span>
								</a>
								<a
									data-sveltekit-preload-data="hover"
									href="/blogs"
									class="hover:text-muted-foreground group flex items-center space-x-3 text-sm font-medium transition-colors"
								>
									<div class="bg-foreground h-px transition-all group-hover:w-2"></div>
									<span>Blogs</span>
								</a>
								<a
									data-sveltekit-preload-data="hover"
									href="/links"
									class="hover:text-muted-foreground group flex items-center space-x-3 text-sm font-medium transition-colors"
								>
									<div class="bg-foreground h-px transition-all group-hover:w-2"></div>
									<span>Links</span>
								</a>
							</div>
						</div>
					</div>

					<!-- Tech Stack -->
					<div class={`${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 0.5s;">
						<div class="border-foreground border-l-4 pl-6">
							<h4 class="text-muted-foreground mb-4 text-sm font-medium tracking-wider uppercase">
								Built With
							</h4>
							<div class="space-y-2 text-sm">
								<div>SvelteKit</div>
								<div>Tailwind CSS</div>
								<div>TypeScript</div>
								<div>Cloudflare</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>

		<!-- Bottom Section -->
		<div
			class={`border-border border-t pt-8 ${mounted ? 'opacity-100' : 'opacity-0'}`}
			style="animation-delay: 0.6s;"
		>
			<div class="flex flex-col space-y-4 md:flex-row md:justify-between md:space-y-0">
				<div class="text-muted-foreground text-sm font-light">
					© {currentYear} Debarshee Chakraborty. All rights reserved.
				</div>
				<div class="text-muted-foreground text-sm font-light">
					Designed with Swiss typography principles
				</div>
			</div>
		</div>
	</div>
</footer>
