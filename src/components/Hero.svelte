<script lang="ts">
	let mounted = false;

	import { onMount } from 'svelte';

	onMount(() => {
		mounted = true;
	});
</script>

<section id="hero" class="relative flex min-h-screen items-center">
	<!-- Grid Lines Overlay for Swiss Layout -->
	<div class="pointer-events-none absolute inset-0 opacity-5">
		<div class="grid h-full grid-cols-12 gap-8">
			{#each Array(12) as _, i}
				<div class="border-foreground border-r"></div>
			{/each}
		</div>
	</div>

	<!-- Swiss Grid Container -->
	<div class="grid w-full grid-cols-12 gap-8">
		<!-- Large Typography Section -->
		<div class="col-span-12 lg:col-span-7">
			<div class="space-y-16">
				<!-- Primary Headline -->
				<div class="relative">
					<div class="text-muted-foreground/20 mb-4 font-mono text-xs tracking-[0.2em] uppercase">
						001
					</div>
					<h1
						class={`text-6xl leading-[0.85] font-black tracking-[-0.02em] uppercase md:text-7xl lg:text-8xl xl:text-9xl ${mounted ? 'translate-y-0 opacity-100' : 'translate-y-8 opacity-0'}`}
						style="transition: all 0.8s cubic-bezier(0.25, 0.1, 0.25, 1);"
					>
						DINO
						<br />
						CAN
						<br />
						<span class="text-muted-foreground">CODE</span>
					</h1>
				</div>

				<!-- Functional Statement -->
				<div
					class={`space-y-8 ${mounted ? 'translate-y-0 opacity-100' : 'translate-y-8 opacity-0'}`}
					style="transition: all 0.8s cubic-bezier(0.25, 0.1, 0.25, 1) 0.2s;"
				>
					<div class="border-foreground border-l-4 pl-8">
						<h2 class="max-w-lg text-lg leading-relaxed font-light md:text-xl">
							Backend and Machine Learning Engineer specializing in scalable systems and AI
							solutions
						</h2>
					</div>
				</div>
			</div>
		</div>

		<!-- Information Panel -->
		<div class="col-span-12 lg:col-span-5">
			<div
				class={`space-y-16 ${mounted ? 'translate-y-0 opacity-100' : 'translate-y-8 opacity-0'}`}
				style="transition: all 0.8s cubic-bezier(0.25, 0.1, 0.25, 1) 0.4s;"
			>
				<!-- Personal Information -->
				<div class="space-y-8">
					<div class="border-foreground border-l-4 pl-8">
						<div class="text-muted-foreground mb-4 font-mono text-xs tracking-[0.2em] uppercase">
							Personal
						</div>
						<div class="space-y-4 text-sm">
							<div class="grid grid-cols-2 gap-x-8 gap-y-3">
								<div>
									<div class="text-muted-foreground font-mono text-xs uppercase">Name</div>
									<div class="font-medium">Debarshee Chakraborty</div>
								</div>
								<div>
									<div class="text-muted-foreground font-mono text-xs uppercase">Location</div>
									<div class="font-medium">Kolkata, India</div>
								</div>
								<div>
									<div class="text-muted-foreground font-mono text-xs uppercase">Status</div>
									<div class="flex items-center gap-2 font-medium">
										<div class="h-2 w-2 rounded-full bg-green-500"></div>
										Available
									</div>
								</div>
								<div>
									<div class="text-muted-foreground font-mono text-xs uppercase">Experience</div>
									<div class="font-medium">2+ Years</div>
								</div>
							</div>
						</div>
					</div>
				</div>

				<!-- Technical Focus -->
				<div class="space-y-8">
					<div class="border-foreground border-l-4 pl-8">
						<div class="text-muted-foreground mb-4 font-mono text-xs tracking-[0.2em] uppercase">
							Technical Focus
						</div>
						<div class="space-y-3 text-sm">
							<div class="border-border flex items-center justify-between border-b py-2">
								<span class="font-medium">Backend Development</span>
								<span class="text-muted-foreground font-mono text-xs">PRIMARY</span>
							</div>
							<div class="border-border flex items-center justify-between border-b py-2">
								<span class="font-medium">Machine Learning</span>
								<span class="text-muted-foreground font-mono text-xs">PRIMARY</span>
							</div>
							<div class="border-border flex items-center justify-between border-b py-2">
								<span class="font-medium">DevOps & Cloud</span>
								<span class="text-muted-foreground font-mono text-xs">SECONDARY</span>
							</div>
						</div>
					</div>
				</div>

				<!-- Primary Technologies -->
				<div class="space-y-8">
					<div class="border-foreground border-l-4 pl-8">
						<div class="text-muted-foreground mb-4 font-mono text-xs tracking-[0.2em] uppercase">
							Core Stack
						</div>
						<div class="grid grid-cols-2 gap-2 font-mono text-xs uppercase">
							<div class="border-foreground border p-2 text-center">Python</div>
							<div class="border-foreground border p-2 text-center">Java</div>
							<div class="border-foreground border p-2 text-center">Go</div>
							<div class="border-foreground border p-2 text-center">TypeScript</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>
