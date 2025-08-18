<script lang="ts">
	const currentYear = new Date().getFullYear();
</script>

<footer class="border-t border-gray-800 bg-black py-12">
	<div class="mx-auto max-w-4xl px-8 text-center">
		<div class="mb-8">
			<h3 class="mb-4 text-2xl font-bold text-white">Let's Build Something Amazing Together</h3>
			<p class="mb-6 text-gray-400">
				I'm always interested in new opportunities and exciting projects.
			</p>
			<a
				href="mailto:hello@example.com"
				class="inline-block rounded-full bg-white px-8 py-3 font-medium text-black transition-colors hover:bg-gray-200"
			>
				Say Hello
			</a>
		</div>

		<div class="border-t border-gray-800 pt-8">
			<p class="text-sm text-gray-500">
				© {currentYear} Alex Developer. Built with SvelteKit and Tailwind CSS.
			</p>
		</div>
	</div>
</footer>
