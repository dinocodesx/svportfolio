<script lang="ts">
	import '../app.css';
	import LoadingScreen from '../components/LoadingScreen.svelte';

	let { children } = $props();
</script>

<LoadingScreen />

<div
	class="bg-background text-foreground mx-auto min-h-screen max-w-6xl px-8 py-16 font-sans antialiased lg:px-16"
>
	{@render children()}
</div>
