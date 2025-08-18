<script lang="ts">
	import blogsData from '../data/blogs.json';

	let blogs: any[] = blogsData;

	function formatDate(dateString: string) {
		return new Date(dateString).toLocaleDateString('en-US', {
			year: 'numeric',
			month: 'long',
			day: 'numeric'
		});
	}
</script>

<section id="blogs" class="bg-gray-900 py-20">
	<div class="mx-auto max-w-4xl">
		<h2 class="mb-12 text-center text-4xl font-bold text-white">Blog Posts</h2>
		<div class="grid gap-8 md:grid-cols-2">
			{#each blogs as blog}
				<article
					class="group rounded-2xl border border-gray-800 bg-black/50 p-6 transition-colors hover:border-gray-600"
				>
					<div class="mb-4">
						<h3
							class="mb-2 text-xl font-semibold text-white transition-colors group-hover:text-gray-300"
						>
							{blog.title}
						</h3>
						<div class="mb-3 flex items-center text-sm text-gray-400">
							<span>{formatDate(blog.date)}</span>
							<span class="mx-2">•</span>
							<span>{blog.readTime}</span>
						</div>
					</div>

					<p class="mb-4 leading-relaxed text-gray-300">
						{blog.excerpt}
					</p>

					<div class="mb-4 flex flex-wrap gap-2">
						{#each blog.tags as tag}
							<span class="rounded-full bg-gray-800 px-3 py-1 text-xs text-gray-300">
								{tag}
							</span>
						{/each}
					</div>

					<a
						href={blog.url}
						class="text-sm font-medium text-gray-400 transition-colors hover:text-white"
					>
						Read More →
					</a>
				</article>
			{/each}
		</div>
	</div>
</section>
