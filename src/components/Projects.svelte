<script lang="ts">
	import projectsData from '../data/projects.json';
	import { onMount } from 'svelte';

	let projects: any[] = projectsData;
	let mounted = false;

	onMount(() => {
		mounted = true;
	});
</script>

<section id="projects" class="mb-10">
	<div class="w-full space-y-12 py-12">
		<div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 1.1s;">
			<div class="flex flex-col items-center justify-center space-y-4 text-center">
				<div class="space-y-2">
					<h2 class="text-3xl font-bold tracking-tighter sm:text-5xl">Check out my latest work</h2>
					<p
						class="text-muted-foreground md:text-xl/relaxed lg:text-base/relaxed xl:text-xl/relaxed"
					>
						I've worked on a variety of projects, from simple websites to complex web applications.
						Here are a few of my favorites.
					</p>
				</div>
			</div>
		</div>
		<div class="mx-auto grid max-w-[900px] grid-cols-1 gap-6 sm:grid-cols-2">
			{#each projects as project, id}
				<div
					class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`}
					style="animation-delay: {1.2 + id * 0.05}s;"
				>
					<div
						class="card group border-border/50 flex h-full flex-col border p-6 transition-all duration-300 hover:shadow-lg"
					>
						<!-- Project Image Placeholder -->
						<div
							class="from-muted to-muted/50 relative mb-6 flex h-48 items-center justify-center overflow-hidden rounded-lg bg-gradient-to-br"
						>
							<div class="bg-secondary/60 h-20 w-20 rounded-xl backdrop-blur-sm"></div>
							<div class="absolute inset-0 bg-gradient-to-t from-black/10 to-transparent"></div>
						</div>

						<div class="flex flex-1 flex-col space-y-4">
							<div class="flex items-start justify-between gap-3">
								<h3 class="flex-1 text-lg leading-tight font-semibold">
									{project.title}
								</h3>
								{#if project.featured}
									<span
										class="shrink-0 rounded-full bg-blue-600 px-2 py-1 text-xs font-medium text-white"
									>
										Featured
									</span>
								{/if}
							</div>

							<p class="text-muted-foreground flex-1 text-sm leading-relaxed">
								{project.description}
							</p>

							<div class="flex flex-wrap gap-2">
								{#each project.technologies as tech}
									<span
										class="bg-muted text-muted-foreground border-border/50 rounded-md border px-2 py-1 text-xs font-medium"
									>
										{tech}
									</span>
								{/each}
							</div>

							<div class="border-border/30 mt-auto flex gap-6 border-t pt-4">
								<a
									href={project.github}
									target="_blank"
									rel="noopener noreferrer"
									class="text-muted-foreground flex items-center gap-1 text-sm font-medium transition-colors hover:text-blue-600"
								>
									<svg class="h-4 w-4" fill="currentColor" viewBox="0 0 24 24">
										<path
											d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"
										/>
									</svg>
									GitHub
								</a>
								<a
									href={project.live}
									target="_blank"
									rel="noopener noreferrer"
									class="text-muted-foreground flex items-center gap-1 text-sm font-medium transition-colors hover:text-blue-600"
								>
									<svg class="h-4 w-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
										<path
											stroke-linecap="round"
											stroke-linejoin="round"
											stroke-width="2"
											d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14"
										/>
									</svg>
									Live Demo
								</a>
							</div>
						</div>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>
