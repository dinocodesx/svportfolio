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
  <meta name="description" content="Read my latest blog posts about machine learning, web development, and technology." />
</svelte:head>

<main class="flex flex-col min-h-[100dvh] space-y-10">
  <section class="mb-10">
    <div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`}>
      <div class="space-y-4 text-center mb-12">
        <div class="inline-block rounded-lg bg-foreground text-background px-3 py-1 text-sm">
          Blog
        </div>
        <h1 class="text-3xl font-bold tracking-tighter sm:text-5xl">
          Latest Posts
        </h1>
        <p class="text-muted-foreground md:text-xl/relaxed lg:text-base/relaxed xl:text-xl/relaxed max-w-2xl mx-auto">
          Thoughts on machine learning, web development, and the latest in technology.
        </p>
      </div>
    </div>
    
    <div class="grid gap-6">
      {#each blogs as blog, id}
        <article class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: {0.1 + id * 0.05}s;">
          <div class="card p-6 hover:shadow-md transition-shadow group">
            <div class="space-y-3">
              <div class="flex items-center text-sm text-muted-foreground">
                <time>{formatDate(blog.date)}</time>
                <span class="mx-2">•</span>
                <span>{blog.readTime}</span>
              </div>
              
              <h2 class="text-xl font-semibold group-hover:text-muted-foreground transition-colors">
                {blog.title}
              </h2>
              
              <p class="text-muted-foreground leading-relaxed">
                {blog.excerpt}
              </p>
              
              <div class="flex flex-wrap gap-2 pt-2">
                {#each blog.tags as tag}
                  <span class="badge badge-outline text-xs">{tag}</span>
                {/each}
              </div>
              
              <div class="pt-2">
                <a 
                  href={blog.url}
                  class="text-muted-foreground hover:text-foreground transition-colors text-sm font-medium"
                >
                  Read More →
                </a>
              </div>
            </div>
          </div>
        </article>
      {/each}
    </div>
    
    <!-- Back to home link -->
    <div class="mt-12 text-center">
      <a 
        href="/"
        class="text-muted-foreground hover:text-foreground transition-colors text-sm font-medium"
      >
        ← Back to Home
      </a>
    </div>
  </section>
</main>