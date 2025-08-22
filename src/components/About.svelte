<script lang="ts">
	let mounted = false;

	import { onMount } from 'svelte';

	onMount(() => {
		mounted = true;
	});
</script>

<section id="about" class="relative">
	<!-- Section Number -->
	<div
		class={`absolute top-0 -left-16 ${mounted ? 'opacity-100' : 'opacity-0'}`}
		style="animation-delay: 0.2s;"
	>
		<div class="text-muted-foreground/20 text-8xl font-black select-none">01</div>
	</div>

	<!-- Content Grid -->
	<div class="grid grid-cols-12 gap-8">
		<!-- Section Header -->
		<div class="col-span-12">
			<div class={`${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 0.3s;">
				<div class="mb-12 flex items-center space-x-8">
					<h2 class="text-4xl font-black tracking-wider uppercase">About</h2>
					<div class="bg-foreground h-px flex-1"></div>
				</div>
			</div>
		</div>

		<!-- Main Content -->
		<div class="col-span-12 lg:col-span-8">
			<div
				class={`space-y-8 ${mounted ? 'opacity-100' : 'opacity-0'}`}
				style="animation-delay: 0.4s;"
			>
				<p class="text-xl leading-relaxed font-light">
					I'm a certified TensorFlow ML Engineer with publications at SciPyConf. Passionate about
					building scalable machine learning solutions and contributing to the open source
					community.
				</p>

				<p class="text-muted-foreground text-lg leading-relaxed font-light">
					When I'm not coding, you can find me writing research papers, mentoring aspiring
					developers, or exploring the latest in AI and machine learning technologies. I believe in
					creating technology that makes a positive impact on society.
				</p>

				<!-- Checkout my Blogs Button -->
				<div class="mt-12">
					<a
						href="/blogs"
						class="dark:bg-swiss-dark inline-block border-2 border-black bg-white px-8 py-4 font-mono text-sm tracking-wider uppercase transition-colors duration-200 hover:bg-black hover:text-white dark:border-white dark:hover:bg-white dark:hover:text-black"
					>
						Checkout my Blogs
					</a>
				</div>
			</div>
		</div>

		<!-- Info Panel -->
		<div class="col-span-12 lg:col-span-4">
			<div
				class={`space-y-8 ${mounted ? 'opacity-100' : 'opacity-0'}`}
				style="animation-delay: 0.5s;"
			>
				<div class="border-foreground border-l-4 pl-6">
					<h3 class="text-muted-foreground mb-3 text-sm font-medium tracking-wider uppercase">
						Expertise
					</h3>
					<ul class="space-y-2 text-sm">
						<li>Machine Learning</li>
						<li>Deep Learning</li>
						<li>Computer Vision</li>
						<li>Natural Language Processing</li>
					</ul>
				</div>

				<div class="border-foreground border-l-4 pl-6">
					<h3 class="text-muted-foreground mb-3 text-sm font-medium tracking-wider uppercase">
						Tools
					</h3>
					<ul class="space-y-2 text-sm">
						<li>TensorFlow & PyTorch</li>
						<li>Python & Scala</li>
						<li>AWS & Google Cloud</li>
						<li>Docker & Kubernetes</li>
					</ul>
				</div>
			</div>
		</div>
	</div>
</section>
