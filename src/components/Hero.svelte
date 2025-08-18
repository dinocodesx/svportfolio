<script lang="ts">
	let mounted = false;

	import { onMount } from 'svelte';

	onMount(() => {
		mounted = true;
	});
</script>

<section id="hero" class="mb-10">
	<div class="mx-auto w-full space-y-8">
		<div class="flex flex-col space-y-1.5">
			<h1
				class={`fade-in text-3xl font-bold tracking-tighter sm:text-5xl xl:text-6xl/none ${mounted ? 'opacity-100' : 'opacity-0'}`}
			>
				Hi, I'm Alex
			</h1>
			<p
				class={`text-muted-foreground fade-in max-w-[600px] md:text-xl ${mounted ? 'opacity-100' : 'opacity-0'}`}
				style="animation-delay: 0.1s;"
			>
				Machine Learning Engineer, I love building things around ML. I am active on Twitter. Read my
				latest research
			</p>
		</div>
	</div>
</section>
