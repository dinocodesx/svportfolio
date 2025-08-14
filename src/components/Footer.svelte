<script lang="ts">
  const currentYear = new Date().getFullYear();
</script>

<footer class="bg-black border-t border-gray-800 py-12">
  <div class="max-w-4xl mx-auto px-8 text-center">
    <div class="mb-8">
      <h3 class="text-2xl font-bold text-white mb-4">Let's Build Something Amazing Together</h3>
      <p class="text-gray-400 mb-6">
        I'm always interested in new opportunities and exciting projects.
      </p>
      <a
        href="mailto:hello@example.com"
        class="inline-block px-8 py-3 bg-white text-black rounded-full font-medium hover:bg-gray-200 transition-colors"
      >
        Say Hello
      </a>
    </div>
    
    <div class="border-t border-gray-800 pt-8">
      <p class="text-gray-500 text-sm">
        © {currentYear} Alex Developer. Built with SvelteKit and Tailwind CSS.
      </p>
    </div>
  </div>
</footer>
