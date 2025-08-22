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
	<!-- Top Grid Section -->
	<div class="grid min-h-[100dvh] grid-cols-12 gap-8 lg:gap-16">
		<!-- Left Column - Main Content -->
		<div class="col-span-12 space-y-24 lg:col-span-8">
			<Hero />
			<About />
			<Experience />
			<Projects />
		</div>

		<!-- Right Column - Secondary Content -->
		<div class="col-span-12 space-y-16 lg:col-span-4">
			<Skills />
			<Volunteering />
		</div>
	</div>

	<!-- Full Width Contact Section at Bottom -->
	<div class="w-full">
		<Contact />
		<Footer />
	</div>
</main>
