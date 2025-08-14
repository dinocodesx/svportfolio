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

<section id="blogs" class="py-20 bg-gray-900">
  <div class="max-w-4xl mx-auto">
    <h2 class="text-4xl font-bold text-white mb-12 text-center">Blog Posts</h2>
    <div class="grid md:grid-cols-2 gap-8">
      {#each blogs as blog}
        <article class="bg-black/50 rounded-2xl p-6 border border-gray-800 hover:border-gray-600 transition-colors group">
          <div class="mb-4">
            <h3 class="text-xl font-semibold text-white group-hover:text-gray-300 transition-colors mb-2">
              {blog.title}
            </h3>
            <div class="flex items-center text-sm text-gray-400 mb-3">
              <span>{formatDate(blog.date)}</span>
              <span class="mx-2">•</span>
              <span>{blog.readTime}</span>
            </div>
          </div>
          
          <p class="text-gray-300 mb-4 leading-relaxed">
            {blog.excerpt}
          </p>
          
          <div class="flex flex-wrap gap-2 mb-4">
            {#each blog.tags as tag}
              <span class="px-3 py-1 bg-gray-800 text-gray-300 rounded-full text-xs">
                {tag}
              </span>
            {/each}
          </div>
          
          <a 
            href={blog.url}
            class="text-gray-400 hover:text-white transition-colors text-sm font-medium"
          >
            Read More →
          </a>
        </article>
      {/each}
    </div>
  </div>
</section>
