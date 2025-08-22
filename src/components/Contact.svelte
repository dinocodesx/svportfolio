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
		class={`fade-in absolute top-0 -left-16 ${mounted ? 'opacity-100' : 'opacity-0'}`}
		style="animation-delay: 1.5s;"
	>
		<div class="text-muted-foreground/20 text-8xl font-black select-none">04</div>
	</div>

	<div class="space-y-16">
		<!-- Header -->
		<div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 1.6s;">
			<div class="mb-12 flex items-center space-x-8">
				<h2 class="text-4xl font-black tracking-wider uppercase">Contact</h2>
				<div class="bg-foreground h-px flex-1"></div>
			</div>
			<p class="text-muted-foreground max-w-2xl text-xl leading-relaxed font-light">
				Ready to collaborate? Let's discuss how we can work together to build something amazing.
			</p>
		</div>

		<!-- Contact Grid -->
		<div class="grid grid-cols-1 gap-12 lg:grid-cols-3">
			<!-- Email -->
			<div
				class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`}
				style="animation-delay: 1.7s;"
			>
				<div class="space-y-6">
					<div class="border-foreground border-l-4 pl-8">
						<h3 class="text-muted-foreground mb-4 text-xs font-medium tracking-wider uppercase">
							Email
						</h3>
						<a
							href="mailto:debarsheedas2004@gmail.com"
							class="hover:text-muted-foreground block text-lg font-medium transition-colors"
						>
							debarsheedas2004@gmail.com
						</a>
						<p class="text-muted-foreground mt-2 text-sm font-light">
							For formal inquiries and collaboration discussions
						</p>
					</div>
				</div>
			</div>

			<!-- Social Links -->
			<div
				class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`}
				style="animation-delay: 1.8s;"
			>
				<div class="space-y-6">
					<div class="border-foreground border-l-4 pl-8">
						<h3 class="text-muted-foreground mb-4 text-xs font-medium tracking-wider uppercase">
							Connect
						</h3>
						<div class="space-y-3">
							<a
								href="https://linkedin.com/in/debarsheedas2004"
								target="_blank"
								rel="noopener noreferrer"
								class="hover:text-muted-foreground group flex items-center space-x-3 text-sm font-medium transition-colors"
							>
								<div class="bg-foreground h-px w-8 transition-all group-hover:w-12"></div>
								<span>LinkedIn</span>
							</a>
							<a
								href="https://twitter.com/debarshee2004"
								target="_blank"
								rel="noopener noreferrer"
								class="hover:text-muted-foreground group flex items-center space-x-3 text-sm font-medium transition-colors"
							>
								<div class="bg-foreground h-px w-8 transition-all group-hover:w-12"></div>
								<span>Twitter</span>
							</a>
							<a
								href="https://github.com/debarshee2004"
								target="_blank"
								rel="noopener noreferrer"
								class="hover:text-muted-foreground group flex items-center space-x-3 text-sm font-medium transition-colors"
							>
								<div class="bg-foreground h-px w-8 transition-all group-hover:w-12"></div>
								<span>GitHub</span>
							</a>
						</div>
					</div>
				</div>
			</div>

			<!-- Status & Info -->
			<div
				class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`}
				style="animation-delay: 1.9s;"
			>
				<div class="space-y-6">
					<div class="border-foreground border-l-4 pl-8">
						<h3 class="text-muted-foreground mb-4 text-xs font-medium tracking-wider uppercase">
							Availability
						</h3>
						<div class="space-y-3">
							<div class="flex items-center space-x-3">
								<div class="h-3 w-3 rounded-full bg-green-500"></div>
								<span class="text-sm font-medium">Available for work</span>
							</div>
							<div class="text-muted-foreground text-sm font-light">San Francisco, CA</div>
							<div class="text-muted-foreground text-sm font-light">Response time: 24 hours</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>
