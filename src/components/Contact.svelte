<script lang="ts">
	import { onMount } from 'svelte';

	let mounted = false;

	onMount(() => {
		mounted = true;
	});
</script>

<section id="contact" class="mb-10">
	<div class="w-full py-12">
		<div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 1.6s;">
			<div class="mb-8 space-y-6 text-center">
				<h2 class="text-3xl font-bold tracking-tighter sm:text-5xl">Get in Touch</h2>
				<p
					class="text-muted-foreground mx-auto max-w-[600px] md:text-xl/relaxed lg:text-base/relaxed xl:text-xl/relaxed"
				>
					Ready to collaborate? Choose your preferred way to connect with me.
				</p>
			</div>
		</div>

		<div class="mx-auto grid max-w-4xl gap-6 md:grid-cols-2">
			<!-- Email Card -->
			<div
				class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`}
				style="animation-delay: 1.7s;"
			>
				<div class="card group flex h-full flex-col p-6 transition-shadow hover:shadow-md">
					<!-- Email Icon -->
					<div class="bg-muted mb-6 flex h-20 items-center justify-center rounded-lg">
						<svg
							class="text-muted-foreground h-10 w-10"
							fill="none"
							stroke="currentColor"
							viewBox="0 0 24 24"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M3 8l7.89 4.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"
							/>
						</svg>
					</div>

					<div class="flex flex-1 flex-col space-y-4">
						<h3 class="text-xl font-semibold">Send an Email</h3>
						<p class="text-muted-foreground flex-1 text-sm">
							For formal inquiries, collaborations, or detailed discussions, drop me an email and
							I'll get back to you as soon as possible.
						</p>
						<a
							href="mailto:debarshee2004@gmail.com"
							class="mt-auto inline-flex items-center justify-center rounded-md bg-blue-600 px-4 py-2 text-sm font-medium text-white transition-colors hover:bg-blue-700"
						>
							Send Email
						</a>
					</div>
				</div>
			</div>

			<!-- Twitter DM Card -->
			<div
				class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`}
				style="animation-delay: 1.8s;"
			>
				<div class="card group flex h-full flex-col p-6 transition-shadow hover:shadow-md">
					<!-- Twitter Icon -->
					<div class="bg-muted mb-6 flex h-20 items-center justify-center rounded-lg">
						<svg class="text-muted-foreground h-10 w-10" fill="currentColor" viewBox="0 0 24 24">
							<path
								d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"
							/>
						</svg>
					</div>

					<div class="flex flex-1 flex-col space-y-4">
						<h3 class="text-xl font-semibold">Twitter DM</h3>
						<p class="text-muted-foreground flex-1 text-sm">
							For quick questions, casual chats, or just to say hi, shoot me a direct message on
							Twitter and I'll respond when I can.
						</p>
						<a
							href="https://twitter.com/debarshee2004"
							target="_blank"
							rel="noopener noreferrer"
							class="mt-auto inline-flex items-center justify-center rounded-md bg-blue-600 px-4 py-2 text-sm font-medium text-white transition-colors hover:bg-blue-700"
						>
							Send DM
						</a>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>
