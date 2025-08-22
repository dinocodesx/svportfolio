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
		class={`absolute -top-2.5 -left-34 ${mounted ? 'opacity-100' : 'opacity-0'}`}
		style="animation-delay: 1.0s;"
	>
		<div class="text-muted-foreground/20 text-8xl font-black select-none">05</div>
	</div>

	<div class="space-y-16">
		<!-- Header -->
		<div class={`${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 1.1s;">
			<div class="mb-12 flex items-center space-x-8">
				<h2 class="text-4xl font-black tracking-wider uppercase">Projects</h2>
				<div class="bg-foreground h-px flex-1"></div>
			</div>
			<p class="text-muted-foreground max-w-2xl text-xl leading-relaxed font-light">
				Selected work showcasing expertise in machine learning, full-stack development, and
				innovative solutions across various domains.
			</p>
		</div>

		<!-- Projects Grid -->
		<div class="space-y-20">
			{#each projects as project, id}
				<div
					class={`grid grid-cols-12 gap-8 lg:gap-16 ${mounted ? 'opacity-100' : 'opacity-0'}`}
					style="animation-delay: {1.2 + id * 0.1}s;"
				>
					<!-- Project Number & Info -->
					<div class="col-span-12 lg:col-span-4">
						<div class="space-y-6">
							<!-- Project Number -->
							<div class="text-muted-foreground/30 text-6xl font-black">
								{String(id + 1).padStart(2, '0')}
							</div>

							<!-- Project Meta -->
							<div class="space-y-4">
								<div>
									<h3 class="mb-2 text-2xl font-bold">{project.title}</h3>
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
					<div class="col-span-12 lg:col-span-8">
						<div class="space-y-8">
							<!-- Project Visual -->
							<div
								class="bg-muted border-foreground relative aspect-video overflow-hidden border-2"
							>
								<div
									class="from-muted-foreground/10 to-muted-foreground/30 absolute inset-0 bg-gradient-to-br"
								></div>
								<div class="absolute inset-0 flex items-center justify-center">
									<div class="text-muted-foreground/50 text-4xl font-black">
										{project.title.charAt(0)}
									</div>
								</div>
							</div>

							<!-- Technologies & Links -->
							<div class="grid grid-cols-1 gap-8 lg:grid-cols-2">
								<!-- Technologies -->
								<div class="space-y-4">
									<h4 class="text-muted-foreground text-xs font-medium tracking-wider uppercase">
										Technologies
									</h4>
									<div class="space-y-2">
										{#each project.technologies as tech}
											<div class="border-foreground border-l-2 pl-4 text-sm font-medium">
												{tech}
											</div>
										{/each}
									</div>
								</div>

								<!-- Links -->
								<div class="space-y-4">
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
				</div>
			{/each}
		</div>

		<!-- Checkout my Projects Button -->
		<div class="mt-12">
			<a
				href="/blogs"
				class="border-foreground bg-background hover:bg-foreground hover:text-background inline-block border-2 px-8 py-4 font-mono text-sm tracking-[0.1em] uppercase transition-all duration-200"
			>
				Checkout my Projects
			</a>
		</div>
	</div>
</section>
