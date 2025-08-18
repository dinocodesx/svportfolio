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

<section id="skills" class="mb-10">
	<div class="flex min-h-0 flex-col gap-y-3">
		<div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 0.9s;">
			<h2 class="text-xl font-bold">Skills</h2>
		</div>
		<div class="flex flex-wrap gap-1">
			{#each allSkills as skill, id}
				<div
					class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`}
					style="animation-delay: {1.0 + id * 0.05}s;"
				>
					<span class="badge">{skill}</span>
				</div>
			{/each}
		</div>
	</div>
</section>
