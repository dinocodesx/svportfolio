<script lang="ts">
	import { onMount } from 'svelte';

	let mounted = false;

	onMount(() => {
		mounted = true;
	});
</script>

<section id="contact" class="relative">
	<!-- Section Number -->
	<div
		class={`absolute -top-2.5 -left-34 ${mounted ? 'opacity-100' : 'opacity-0'}`}
		style="animation-delay: 1.5s;"
	>
		<div class="text-muted-foreground/20 text-8xl font-black select-none">06</div>
	</div>

	<div class="space-y-16">
		<!-- Header -->
		<div class={`${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 1.6s;">
			<div class="mb-12 flex items-center space-x-8">
				<h2 class="text-4xl font-black tracking-wider uppercase">Contact</h2>
				<div class="bg-foreground h-px flex-1"></div>
			</div>
			<p class="text-muted-foreground max-w-2xl text-xl leading-relaxed font-light">
				Ready to collaborate? Let's discuss how we can work together to build something amazing.
			</p>
		</div>

		<!-- Contact Content -->
		<div class="grid grid-cols-1 gap-16 lg:grid-cols-2">
			<!-- Contact Info & CTA Buttons -->
			<div class="space-y-12">
				<!-- Primary CTA Buttons -->
				<div
					class={`space-y-6 ${mounted ? 'opacity-100' : 'opacity-0'}`}
					style="animation-delay: 1.7s;"
				>
					<h3 class="text-muted-foreground mb-6 text-sm font-medium tracking-wider uppercase">
						Get In Touch
					</h3>

					<div class="space-y-4">
						<!-- Email CTA -->
						<a
							href="mailto:debarshee.chakraborty.work2004@gmail.com"
							class="group border-foreground bg-background hover:bg-foreground hover:text-background flex w-full items-center justify-between border-2 p-6 font-mono text-sm tracking-wider uppercase transition-colors duration-200"
						>
							<div class="flex items-center space-x-4">
								<div
									class="bg-foreground group-hover:bg-background flex h-8 w-8 items-center justify-center"
								>
									<span class="text-background group-hover:text-foreground text-xs font-black"
										>@</span
									>
								</div>
								<span>Send Email</span>
							</div>
							<div class="text-muted-foreground group-hover:text-background/70 text-xs">→</div>
						</a>

						<!-- Twitter CTA -->
						<a
							href="https://x.com/dinocodes69"
							target="_blank"
							rel="noopener noreferrer"
							class="group border-foreground bg-background hover:bg-foreground hover:text-background flex w-full items-center justify-between border-2 p-6 font-mono text-sm tracking-wider uppercase transition-colors duration-200"
						>
							<div class="flex items-center space-x-4">
								<div
									class="bg-foreground group-hover:bg-background flex h-8 w-8 items-center justify-center"
								>
									<span class="text-background group-hover:text-foreground text-xs font-black"
										>X</span
									>
								</div>
								<span>Follow on Twitter</span>
							</div>
							<div class="text-muted-foreground group-hover:text-background/70 text-xs">↗</div>
						</a>
					</div>
				</div>

				<!-- Contact Details -->
				<div class={`${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 1.8s;">
					<div class="border-foreground border-l-4 pl-6">
						<h3 class="text-muted-foreground mb-4 text-xs font-medium tracking-wider uppercase">
							Direct Contact
						</h3>
						<div class="space-y-3">
							<div class="text-sm">
								<span class="text-muted-foreground">Email:</span>
								<br />
								<span class="font-mono">debarshee.chakraborty.work@gmail.com</span>
							</div>
							<div class="text-sm">
								<span class="text-muted-foreground">Response Time:</span>
								<br />
								<span>Usually within 24 hours</span>
							</div>
						</div>
					</div>
				</div>
			</div>

			<!-- Additional Info & Status -->
			<div class="space-y-12">
				<!-- Social Links -->
				<div class={`${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 1.9s;">
					<div class="border-foreground border-l-4 pl-6">
						<h3 class="text-muted-foreground mb-4 text-xs font-medium tracking-wider uppercase">
							Connect Elsewhere
						</h3>
						<div class="space-y-3">
							<a
								href="https://linkedin.com/in/debarsheedas2004"
								target="_blank"
								rel="noopener noreferrer"
								class="hover:text-muted-foreground group flex items-center space-x-3 text-sm font-medium transition-colors"
							>
								<div class="bg-foreground h-px transition-all group-hover:w-2"></div>
								<span>LinkedIn</span>
							</a>
							<a
								data-sveltekit-preload-data="hover"
								href="https://github.com/debarshee2004"
								target="_blank"
								rel="noopener noreferrer"
								class="hover:text-muted-foreground group flex items-center space-x-3 text-sm font-medium transition-colors"
							>
								<div class="bg-foreground h-px transition-all group-hover:w-2"></div>
								<span>GitHub</span>
							</a>
							<a
								data-sveltekit-preload-data="hover"
								href="/links"
								class="hover:text-muted-foreground group flex items-center space-x-3 text-sm font-medium transition-colors"
							>
								<div class="bg-foreground h-px transition-all group-hover:w-2"></div>
								<span>All Links</span>
							</a>
						</div>
					</div>
				</div>

				<!-- Status & Availability -->
				<div class={`${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 2.0s;">
					<div class="border-foreground border-l-4 pl-6">
						<h3 class="text-muted-foreground mb-4 text-xs font-medium tracking-wider uppercase">
							Current Status
						</h3>
						<div class="space-y-3">
							<div class="flex items-center space-x-3">
								<div class="h-3 w-3 rounded-full bg-green-500"></div>
								<span class="text-sm font-medium">Available for opportunities</span>
							</div>
							<div class="text-muted-foreground text-sm">Open to full-time roles</div>
							<div class="text-muted-foreground text-sm">Remote or hybrid preferred</div>
						</div>
					</div>
				</div>

				<!-- What I'm Looking For -->
				<div class={`${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 2.1s;">
					<div class="border-foreground border-l-4 pl-6">
						<h3 class="text-muted-foreground mb-4 text-xs font-medium tracking-wider uppercase">
							What I'm Looking For
						</h3>
						<div class="space-y-2 text-sm">
							<div>• Backend Development roles</div>
							<div>• Machine Learning Engineering roles</div>
							<div>• Open source collaborations</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>
