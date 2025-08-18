<script lang="ts">
	import Hero from '../components/Hero.svelte';
	import About from '../components/About.svelte';
	import Experience from '../components/Experience.svelte';
	import Skills from '../components/Skills.svelte';
	import Projects from '../components/Projects.svelte';
	import Volunteering from '../components/Volunteering.svelte';
	import Contact from '../components/Contact.svelte';
	import Navbar from '../components/Navbar.svelte';
</script>

<svelte:head>
	<title>Alex Developer - Machine Learning Engineer Portfolio</title>
	<meta
		name="description"
		content="Machine Learning Engineer specializing in TensorFlow, PyTorch, and modern AI technologies. View my projects, research, and experience."
	/>
</svelte:head>

<main class="flex min-h-[100dvh] flex-col space-y-10">
	<Hero />
	<About />
	<Experience />
	<Skills />
	<Projects />
	<Volunteering />
	<Contact />
</main>

<Navbar />
