<script lang="ts">
	import linksData from '../data/links.json';

	let links: any[] = linksData;

	function getIcon(iconName: string) {
		const icons: { [key: string]: string } = {
			github: '🐙',
			linkedin: '💼',
			twitter: '🐦',
			email: '📧',
			document: '📄'
		};
		return icons[iconName] || '🔗';
	}
</script>

<section id="links" class="py-20">
	<div class="mx-auto max-w-4xl">
		<h2 class="mb-12 text-center text-4xl font-bold text-white">Connect With Me</h2>
		<div class="grid gap-6 md:grid-cols-2 lg:grid-cols-3">
			{#each links as link}
				<a
					href={link.url}
					target="_blank"
					rel="noopener noreferrer"
					class="group rounded-2xl border border-gray-800 bg-gray-900 p-6 transition-all hover:border-gray-600 hover:bg-gray-800"
				>
					<div class="mb-3 flex items-center">
						<span class="mr-3 text-2xl">{getIcon(link.icon)}</span>
						<h3
							class="text-lg font-semibold text-white transition-colors group-hover:text-gray-300"
						>
							{link.name}
						</h3>
					</div>
					<p class="text-sm text-gray-400">
						{link.description}
					</p>
				</a>
			{/each}
		</div>
	</div>
</section>
