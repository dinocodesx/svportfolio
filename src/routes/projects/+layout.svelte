<script lang="ts">
	let { children } = $props();
</script>

<svelte:head>
	<title>Projects - Dino Codes</title>
	<meta
		name="description"
		content="A showcase of projects and technical work by Dino Codes, featuring machine learning, backend development, and full-stack applications."
	/>
</svelte:head>

<div class="space-y-8">
	{@render children()}
</div>
