<script lang="ts">
	import experienceData from '../data/experience.json';
	import { onMount } from 'svelte';

	let experiences: any[] = experienceData;
	let mounted = false;

	onMount(() => {
		mounted = true;
	});
</script>

<section id="work" class="relative">
	<!-- Section Number -->
	<div
		class={`absolute -top-2.5 -left-34 ${mounted ? 'opacity-100' : 'opacity-0'}`}
		style="animation-delay: 0.4s;"
	>
		<div class="text-muted-foreground/20 text-8xl font-black select-none">02</div>
	</div>

	<div class="space-y-12">
		<!-- Header -->
		<div class={`${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 0.5s;">
			<div class="mb-12 flex items-center space-x-8">
				<h2 class="text-4xl font-black tracking-wider uppercase">Experience</h2>
				<div class="bg-foreground h-px flex-1"></div>
			</div>
		</div>

		<!-- Experience Timeline -->
		<div class="space-y-16">
			{#each experiences as work, id}
				<div
					class={`grid grid-cols-12 gap-8 ${mounted ? 'opacity-100' : 'opacity-0'}`}
					style="animation-delay: {0.6 + id * 0.1}s;"
				>
					<!-- Timeline -->
					<div class="col-span-12 lg:col-span-3">
						<div class="space-y-2">
							<div class="text-muted-foreground text-xs font-medium tracking-wider uppercase">
								{work.duration}
							</div>
							<div class="text-muted-foreground text-sm">{work.location}</div>
						</div>
					</div>

					<!-- Content -->
					<div class="col-span-12 lg:col-span-9">
						<div class="border-foreground space-y-4 border-l-4 pl-8">
							<div>
								<h3 class="mb-1 text-2xl font-bold">{work.company}</h3>
								<div class="text-muted-foreground text-lg font-light">{work.title}</div>
							</div>

							{#if work.description}
								<p class="text-muted-foreground leading-relaxed font-light">
									{work.description}
								</p>
							{/if}

							<!-- Technologies -->
							<div class="space-y-2">
								<div class="text-muted-foreground text-xs font-medium tracking-wider uppercase">
									Tech Stack
								</div>
								<div class="flex flex-wrap gap-2">
									{#each work.technologies as tech}
										<span class="bg-muted py-1 text-xs font-medium tracking-wider uppercase">
											{tech}
										</span>
									{/each}
								</div>
							</div>
						</div>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>
