<script lang="ts">
  let mounted = false;
  
  import { onMount } from 'svelte';
  
  onMount(() => {
    mounted = true;
  });
</script>

<section id="hero" class="mb-10">
  <div class="mx-auto w-full space-y-8">
    <div class="gap-2 flex justify-between">
      <div class="flex-col flex flex-1 space-y-1.5">
        <h1 class={`text-3xl font-bold tracking-tighter sm:text-5xl xl:text-6xl/none fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`}>
          Hi, I'm Alex
        </h1>
        <p class={`max-w-[600px] text-muted-foreground md:text-xl fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 0.1s;">
          Machine Learning Engineer, I love building things around ML. I am active on Twitter. Read my latest research
        </p>
      </div>
      <div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 0.2s;">
        <div class="size-28 border rounded-full bg-muted flex items-center justify-center overflow-hidden">
          <img 
            src="https://github.com/debarshee2004.png" 
            alt="Debarshee Das"
            class="w-full h-full object-cover"
          />
        </div>
      </div>
    </div>
  </div>
</section>
