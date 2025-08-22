<script lang="ts">
	import { onMount } from 'svelte';

	let mounted = false;
	onMount(() => {
		mounted = true;
	});
</script>

<svelte:head>
	<title>Projects - Coming Soon | Debarshee Das</title>
	<meta
		name="description"
		content="Projects portfolio page coming soon. Stay tuned for exciting updates."
	/>
</svelte:head>

<main class="flex items-center justify-center text-center" style="height: 80dvh">
	<div class={`${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 1s;">
		<div class="flex items-center justify-center">
			<h1 class="text-4xl font-black tracking-wider uppercase md:text-6xl">Projects Coming Soon</h1>
		</div>
	</div>
</main>
