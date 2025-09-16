<script lang="ts">
	let { children } = $props();
</script>

<svelte:head>
	<title>Talks - Dino Codes</title>
	<meta
		name="description"
		content="Technical talks and presentations by Dino Codes on machine learning, backend engineering, and modern technologies."
	/>
</svelte:head>

<div class="space-y-8">
	{@render children()}
</div>
