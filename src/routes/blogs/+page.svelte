<script lang="ts">
	import blogsData from '../../data/blogs.json';
	import { onMount } from 'svelte';

	let blogs: any[] = blogsData;
	let mounted = false;

	onMount(() => {
		mounted = true;
	});

	function formatDate(dateString: string) {
		return new Date(dateString).toLocaleDateString('en-US', {
			year: 'numeric',
			month: 'long',
			day: 'numeric'
		});
	}
</script>

<svelte:head>
	<title>Blog Posts - Debarshee Das</title>
	<meta
		name="description"
		content="Read my latest blog posts about machine learning, web development, and technology."
	/>
</svelte:head>

<main class="flex min-h-[100dvh] flex-col space-y-10">
	<section class="mb-10">
		<div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`}>
			<div class="mb-12 space-y-4 text-center">
				<h1 class="text-3xl font-bold tracking-tighter sm:text-5xl">Latest Posts</h1>
				<p
					class="text-muted-foreground mx-auto max-w-2xl md:text-xl/relaxed lg:text-base/relaxed xl:text-xl/relaxed"
				>
					Thoughts on machine learning, web development, and the latest in technology.
				</p>
			</div>
		</div>

		<div class="space-y-4">
			{#each blogs as blog, id}
				<div
					class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`}
					style="animation-delay: {0.1 + id * 0.05}s;"
				>
					<div
						class="hover:bg-muted/50 group flex items-center rounded px-2 py-2 transition-colors"
					>
						<div class="min-w-0 shrink-0">
							<a
								href={blog.url}
								class="text-foreground hover:text-muted-foreground font-medium transition-colors"
							>
								{blog.title}
							</a>
						</div>
						<div
							class="border-muted-foreground/30 mx-4 min-w-[20px] flex-1 border-b border-dotted"
						></div>
						<div class="text-muted-foreground shrink-0 text-sm whitespace-nowrap">
							{formatDate(blog.date)}
						</div>
					</div>
				</div>
			{/each}
		</div>

		<!-- Back to home link -->
		<div class="mt-12 text-center">
			<a
				href="/"
				class="text-muted-foreground hover:text-foreground text-sm font-medium transition-colors"
			>
				← Back to Home
			</a>
		</div>
	</section>
</main>
