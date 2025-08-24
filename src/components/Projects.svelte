<script lang="ts">
	import projectsData from '../data/projects.json';
	import { onMount } from 'svelte';

	let projects: any[] = projectsData;
	let mounted = false;

	onMount(() => {
		mounted = true;
	});
</script>

<section id="projects" class="relative">
	<!-- Section Number -->
	<div
		class={`absolute -top-2.5 -left-16 sm:-left-24 lg:-left-34 ${mounted ? 'opacity-100' : 'opacity-0'}`}
		style="animation-delay: 1.0s;"
	>
		<div class="text-muted-foreground/20 text-4xl font-black select-none sm:text-6xl lg:text-8xl">
			05
		</div>
	</div>

	<div class="space-y-12 sm:space-y-16">
		<!-- Header -->
		<div class={`${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 1.1s;">
			<div
				class="mb-8 flex flex-col space-y-4 sm:mb-12 sm:flex-row sm:items-center sm:space-y-0 sm:space-x-8"
			>
				<h2 class="text-2xl font-black tracking-wider uppercase sm:text-3xl lg:text-4xl">
					Projects
				</h2>
				<div class="bg-foreground h-px flex-1"></div>
			</div>
			<p
				class="text-muted-foreground max-w-2xl text-base leading-relaxed font-light sm:text-lg lg:text-xl"
			>
				Selected work showcasing expertise in machine learning, full-stack development, and
				innovative solutions across various domains.
			</p>
		</div>

		<!-- Projects Grid -->
		<div class="space-y-16 sm:space-y-20">
			{#each projects as project, id}
				<div
					class={`grid grid-cols-1 gap-8 lg:grid-cols-12 lg:gap-16 ${mounted ? 'opacity-100' : 'opacity-0'}`}
					style="animation-delay: {1.2 + id * 0.1}s;"
				>
					<!-- Project Number & Info -->
					<div class="lg:col-span-4">
						<div class="space-y-4 sm:space-y-6">
							<!-- Project Number -->
							<div class="text-muted-foreground/30 text-4xl font-black sm:text-5xl lg:text-6xl">
								{String(id + 1).padStart(2, '0')}
							</div>

							<!-- Project Meta -->
							<div class="space-y-3 sm:space-y-4">
								<div>
									<h3 class="mb-2 text-xl font-bold sm:text-2xl">{project.title}</h3>
									{#if project.featured}
										<div
											class="bg-foreground text-background inline-block px-3 py-1 text-xs font-medium tracking-wider uppercase"
										>
											Featured
										</div>
									{/if}
								</div>

								<p class="text-muted-foreground leading-relaxed font-light">
									{project.description}
								</p>
							</div>
						</div>
					</div>

					<!-- Project Details -->
					<div class="lg:col-span-8">
						<div class="space-y-6 sm:space-y-8">
							<!-- Project Visual -->
							<div
								class="bg-muted border-foreground relative aspect-video overflow-hidden border-2"
							>
								<div
									class="from-muted-foreground/10 to-muted-foreground/30 absolute inset-0 bg-gradient-to-br"
								></div>
								<div class="absolute inset-0 flex items-center justify-center">
									<div class="text-muted-foreground/50 text-2xl font-black sm:text-3xl lg:text-4xl">
										{project.title.charAt(0)}
									</div>
								</div>
							</div>

							<!-- Technologies & Links -->
							<div class="grid grid-cols-1 gap-6 sm:gap-8 lg:grid-cols-2">
								<!-- Technologies -->
								<div class="space-y-3 sm:space-y-4">
									<h4 class="text-muted-foreground text-xs font-medium tracking-wider uppercase">
										Technologies
									</h4>
									<div class="space-y-2">
										{#each project.technologies as tech}
											<div class="border-foreground border-l-2 pl-3 text-sm font-medium sm:pl-4">
												{tech}
											</div>
										{/each}
									</div>
								</div>
							</div>

							<!-- Links -->
							<div class="space-y-3 sm:space-y-4">
								<h4 class="text-muted-foreground text-xs font-medium tracking-wider uppercase">
									Links
								</h4>
								<div class="space-y-3">
									{#if project.github}
										<a
											href={project.github}
											target="_blank"
											rel="noopener noreferrer"
											class="hover:text-muted-foreground group flex items-center text-sm font-medium transition-colors"
										>
											<div class="h-px transition-all group-hover:w-2"></div>
											<span>View on GitHub</span>
										</a>
									{/if}
									{#if project.live}
										<a
											href={project.live}
											target="_blank"
											rel="noopener noreferrer"
											class="hover:text-muted-foreground group flex items-center text-sm font-medium transition-colors"
										>
											<div class="h-px transition-all group-hover:w-2"></div>
											<span>Live Demo</span>
										</a>
									{/if}
								</div>
							</div>
						</div>
					</div>
				</div>
			{/each}
		</div>

		<!-- Checkout my Projects Button -->
		<div class="mt-8 sm:mt-12">
			<a
				target="_blank"
				href="https://github.com/debarshee2004"
				class="border-foreground bg-background hover:bg-foreground hover:text-background inline-block border-2 px-6 py-3 font-mono text-xs tracking-[0.1em] uppercase transition-all duration-200 sm:px-8 sm:py-4 sm:text-sm"
			>
				Checkout more Projects
			</a>
		</div>
	</div>
</section>
