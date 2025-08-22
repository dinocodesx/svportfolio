<script lang="ts">
	let mounted = false;

	import { onMount } from 'svelte';

	onMount(() => {
		mounted = true;
	});
</script>

<section id="hero" class="relative">
	<!-- Large Typography -->
	<div class="space-y-12">
		<!-- Main Heading with Swiss Typography -->
		<div class="relative">
			<h1
				class={`text-8xl leading-none font-black tracking-tighter lg:text-9xl ${mounted ? 'opacity-100' : 'opacity-0'}`}
			>
				DINO CAN
				<br />
				<span class="text-muted-foreground">CODE</span>
			</h1>

			<!-- Geometric Element -->
			<div
				class={`bg-foreground absolute -top-4 -right-4 h-32 w-32 ${mounted ? 'opacity-100' : 'opacity-0'}`}
				style="animation-delay: 0.2s;"
			></div>
		</div>

		<!-- Subtitle with Swiss Grid -->
		<div class="grid grid-cols-12 gap-8">
			<div class="col-span-1">
				<div class="bg-foreground mt-4 h-px w-full"></div>
			</div>
			<div class="col-span-11">
				<p
					class={`text-muted-foreground max-w-lg text-lg leading-relaxed font-light ${mounted ? 'opacity-100' : 'opacity-0'}`}
					style="animation-delay: 0.3s;"
				>
					Hello i am Debarshee Chakraborty, i am <span class="font-bold underline">Backend</span>
					and <span class="font-bold underline">Machine Learning Engineer</span> mainly working with
					<span class="font-bold underline">Python</span>,
					<span class="font-bold underline">Java</span>, <span class="font-bold underline">Go</span>
					and
					<span class="font-bold underline">Typescript</span>.
				</p>
			</div>
		</div>

		<!-- Functional Information Grid -->
		<div
			class={`grid grid-cols-12 gap-8 pt-16 ${mounted ? 'opacity-100' : 'opacity-0'}`}
			style="animation-delay: 0.4s;"
		>
			<div class="col-span-3">
				<div class="space-y-2">
					<div class="text-muted-foreground text-xs font-medium tracking-wider uppercase">
						Location
					</div>
					<div class="font-medium">Kolkata, WB, India</div>
				</div>
			</div>
			<div class="col-span-3">
				<div class="space-y-2">
					<div class="text-muted-foreground text-xs font-medium tracking-wider uppercase">
						Status
					</div>
					<div class="font-medium">Available for work</div>
				</div>
			</div>
			<div class="col-span-3">
				<div class="space-y-2">
					<div class="text-muted-foreground text-xs font-medium tracking-wider uppercase">
						Focus
					</div>
					<div class="font-medium">Backend and AI/ML</div>
				</div>
			</div>
			<div class="col-span-3">
				<div class="space-y-2">
					<div class="text-muted-foreground text-xs font-medium tracking-wider uppercase">
						Years
					</div>
					<div class="font-medium">2+ Experience</div>
				</div>
			</div>
		</div>
	</div>
</section>
