<script lang="ts">
	import Hero from '../components/Hero.svelte';
	import About from '../components/About.svelte';
	import Experience from '../components/Experience.svelte';
	import Skills from '../components/Skills.svelte';
	import Projects from '../components/Projects.svelte';
	import Volunteering from '../components/Volunteering.svelte';
	import Contact from '../components/Contact.svelte';
	import Footer from '../components/Footer.svelte';
</script>

<svelte:head>
	<title>Dino Codes - Engineer Portfolio</title>
	<meta
		name="description"
		content="Machine Learning and Backend Engineer specializing in Python, Java, Go and Typescript, and modern AI technologies."
	/>
</svelte:head>

<main class="space-y-24">
	<Hero />
	<About />
	<Experience />
	<Skills />
	<Volunteering />
	<Projects />
	<Contact />
	<Footer />
</main>
