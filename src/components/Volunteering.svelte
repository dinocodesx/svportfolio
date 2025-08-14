<script lang="ts">
	import volunteerData from '../data/volunteer.json';
	import { onMount } from 'svelte';

	let volunteer: any[] = volunteerData;
	let mounted = false;

	onMount(() => {
		mounted = true;
	});
</script>

<section id="volunteering" class="mb-10">
	<div class="w-full space-y-12 py-12">
		<div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 1.3s;">
			<div class="flex flex-col items-center justify-center space-y-4 text-center">
				<div class="space-y-2">
					<h2 class="text-3xl font-bold tracking-tighter sm:text-5xl">Giving Back</h2>
					<p
						class="text-muted-foreground md:text-xl/relaxed lg:text-base/relaxed xl:text-xl/relaxed"
					>
						I believe in using my skills to make a positive impact in the community through
						mentoring and open source contributions.
					</p>
				</div>
			</div>
		</div>
		<div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 1.4s;">
			<ul class="mb-4 ml-4 divide-y divide-dashed border-l">
				{#each volunteer as vol, id}
					<div
						class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`}
						style="animation-delay: {1.5 + id * 0.05}s;"
					>
						<li class="relative ml-6 py-6">
							<div class="flex flex-1 flex-col justify-start gap-2">
								<time class="text-muted-foreground text-xs">{vol.duration}</time>
								<h3 class="text-base font-semibold">{vol.title}</h3>
								<h4 class="text-muted-foreground text-sm">{vol.organization}</h4>
								<p class="text-muted-foreground text-sm">{vol.description}</p>
							</div>
						</li>
					</div>
				{/each}
			</ul>
		</div>
	</div>
</section>
