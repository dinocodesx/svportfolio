<script lang="ts">
	import '../app.css';
	import LoadingScreen from '../components/LoadingScreen.svelte';

	let { children } = $props();
</script>

<LoadingScreen />

<div class="bg-background mx-auto min-h-screen max-w-2xl px-6 py-12 font-sans antialiased sm:py-24">
	{@render children()}
</div>
