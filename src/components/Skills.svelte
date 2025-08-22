<script lang="ts">
	import skillsData from '../data/skills.json';
	import { onMount } from 'svelte';

	let skills: any[] = skillsData;
	let mounted = false;

	// Flatten skills from categories
	let allSkills: string[] = [];
	skills.forEach((category) => {
		category.skills.forEach((skill: any) => {
			allSkills.push(skill.name);
		});
	});

	onMount(() => {
		mounted = true;
	});
</script>

<section id="skills" class="relative">
	<!-- Section Number -->
	<div
		class={`absolute -top-2.5 -left-34 ${mounted ? 'opacity-100' : 'opacity-0'}`}
		style="animation-delay: 0.8s;"
	>
		<div class="text-muted-foreground/20 text-8xl font-black select-none">03</div>
	</div>

	<div class="space-y-16">
		<!-- Header -->
		<div class={`${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 0.9s;">
			<div class="mb-12 flex items-center space-x-8">
				<h2 class="text-4xl font-black tracking-wider uppercase">Skills</h2>
				<div class="bg-foreground h-px flex-1"></div>
			</div>
		</div>

		<!-- Skills Content -->
		<div class="space-y-12">
			<!-- Summary -->
			<div class={`${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 1.0s;">
				<p class="text-muted-foreground max-w-lg text-lg leading-relaxed font-light">
					A diverse technical toolkit spanning machine learning, backend development, and modern web
					technologies.
				</p>
			</div>

			<!-- Skills Categories -->
			<div class="space-y-8">
				{#each skills as category, categoryIndex}
					<div
						class={`${mounted ? 'opacity-100' : 'opacity-0'}`}
						style="animation-delay: {1.1 + categoryIndex * 0.2}s;"
					>
						<div class="border-foreground border-l-4 pl-6">
							<h3 class="text-muted-foreground mb-6 text-sm font-medium tracking-wider uppercase">
								{category.category}
							</h3>

							<!-- Skills Grid -->
							<div class="grid grid-cols-1 gap-3 sm:grid-cols-2 lg:grid-cols-3">
								{#each category.skills as skill, skillIndex}
									<div
										class={`group border-border bg-background hover:bg-muted flex items-center justify-between border p-4 transition-colors duration-200 ${mounted ? 'opacity-100' : 'opacity-0'}`}
										style="animation-delay: {1.2 + categoryIndex * 0.2 + skillIndex * 0.1}s;"
									>
										<div class="space-y-1">
											<div class="text-sm font-medium">{skill.name}</div>
											{#if skill.level}
												<div class="text-muted-foreground text-xs font-light">
													{skill.level}
												</div>
											{/if}
										</div>

										<!-- Skill Level Indicator -->
										{#if skill.proficiency}
											<div class="flex space-x-1">
												{#each Array(5) as _, i}
													<div
														class={`h-2 w-2 ${i < skill.proficiency ? 'bg-foreground' : 'bg-border'}`}
													></div>
												{/each}
											</div>
										{/if}
									</div>
								{/each}
							</div>
						</div>
					</div>
				{/each}
			</div>
		</div>
	</div>
</section>
