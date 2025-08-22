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
		class={`absolute top-0 -left-8 ${mounted ? 'opacity-100' : 'opacity-0'}`}
		style="animation-delay: 0.8s;"
	>
		<div class="text-muted-foreground/30 rotate-90 text-4xl font-black select-none">02</div>
	</div>

	<div class="space-y-8">
		<!-- Header -->
		<div class={`${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 0.9s;">
			<h2 class="mb-4 text-2xl font-black tracking-wider uppercase">Skills</h2>
			<div class="bg-foreground h-px w-full"></div>
		</div>

		<!-- Skills Grid -->
		<div class="space-y-6">
			{#each skills as category, categoryIndex}
				<div
					class={`${mounted ? 'opacity-100' : 'opacity-0'}`}
					style="animation-delay: {1.0 + categoryIndex * 0.1}s;"
				>
					<h3 class="text-muted-foreground mb-3 text-xs font-medium tracking-wider uppercase">
						{category.category}
					</h3>
					<div class="space-y-2">
						{#each category.skills as skill, skillIndex}
							<div
								class={`border-foreground border-l-2 py-1 pl-4 ${mounted ? 'opacity-100' : 'opacity-0'}`}
								style="animation-delay: {1.1 + categoryIndex * 0.1 + skillIndex * 0.05}s;"
							>
								<div class="text-sm font-medium">{skill.name}</div>
							</div>
						{/each}
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>
