<script lang="ts">
  import experienceData from '../data/experience.json';
  import { onMount } from 'svelte';
  
  let experiences: any[] = experienceData;
  let mounted = false;
  
  onMount(() => {
    mounted = true;
  });
</script>

<section id="work" class="mb-10">
  <div class="flex min-h-0 flex-col gap-y-3">
    <div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 0.5s;">
      <h2 class="text-xl font-bold">Work Experience</h2>
    </div>
    {#each experiences as work, id}
      <div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: {0.6 + id * 0.05}s;">
        <div class="card p-4 hover:shadow-md transition-shadow">
          <div class="flex flex-col space-y-1.5">
            <div class="flex flex-col sm:flex-row sm:justify-between sm:items-start">
              <h3 class="font-semibold text-base">{work.company}</h3>
              <div class="text-xs text-muted-foreground">{work.duration}</div>
            </div>
            <div class="text-sm text-muted-foreground">{work.title}</div>
            <div class="text-sm text-muted-foreground">{work.location}</div>
          </div>
          {#if work.description}
            <div class="text-pretty font-sans text-sm text-muted-foreground mt-2">
              {work.description}
            </div>
          {/if}
          <div class="flex flex-wrap gap-1 mt-2">
            {#each work.technologies as tech}
              <span class="badge badge-secondary text-xs">{tech}</span>
            {/each}
          </div>
        </div>
      </div>
    {/each}
  </div>
</section>
