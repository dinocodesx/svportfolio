<script lang="ts">
  import linksData from '../data/links.json';
  import { onMount } from 'svelte';
  
  let links: any[] = linksData;
  let mounted = false;
  
  onMount(() => {
    mounted = true;
  });
  
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

<section id="contact" class="mb-10">
  <div class="grid items-center justify-center gap-4 text-center w-full py-12">
    <div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 1.6s;">
      <div class="space-y-3">
        <div class="inline-block rounded-lg bg-foreground text-background px-3 py-1 text-sm">
          Contact
        </div>
        <h2 class="text-3xl font-bold tracking-tighter sm:text-5xl">
          Get in Touch
        </h2>
        <p class="mx-auto max-w-[600px] text-muted-foreground md:text-xl/relaxed lg:text-base/relaxed xl:text-xl/relaxed">
          Want to chat? Just shoot me a dm{" "}
          <a 
            href="https://twitter.com/username" 
            class="text-blue-600 hover:underline"
          >
            with a direct question on twitter
          </a>{" "}
          and I'll respond whenever I can.
        </p>
      </div>
    </div>
  </div>
</section>
