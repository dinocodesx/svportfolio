<script lang="ts">
	import volunteerData from '../data/volunteer.json';
	import { onMount } from 'svelte';

	let volunteer: any[] = volunteerData;
	let mounted = false;

	onMount(() => {
		mounted = true;
	});
</script>

<section id="volunteering" class="relative">
	<!-- Section Number -->
	<div
		class={`absolute top-0 -left-8 ${mounted ? 'opacity-100' : 'opacity-0'}`}
		style="animation-delay: 1.2s;"
	>
		<div class="text-muted-foreground/30 rotate-90 text-4xl font-black select-none">03</div>
	</div>

	<div class="space-y-8">
		<!-- Header -->
		<div class={`${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 1.3s;">
			<h2 class="mb-4 text-2xl font-black tracking-wider uppercase">Volunteer</h2>
			<div class="bg-foreground h-px w-full"></div>
		</div>

		<!-- Volunteer Timeline -->
		<div class="space-y-6">
			{#each volunteer as vol, id}
				<div
					class={`${mounted ? 'opacity-100' : 'opacity-0'}`}
					style="animation-delay: {1.4 + id * 0.1}s;"
				>
					<div class="border-foreground space-y-3 border-l-4 pl-6">
						<div class="space-y-1">
							<div class="text-muted-foreground text-xs font-medium tracking-wider uppercase">
								{vol.duration}
							</div>
							<h3 class="text-sm font-bold">{vol.title}</h3>
							<div class="text-muted-foreground text-xs font-medium">
								{vol.organization}
							</div>
						</div>
						<p class="text-muted-foreground text-xs leading-relaxed">
							{vol.description}
						</p>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>
