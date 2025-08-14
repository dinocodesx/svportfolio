<script lang="ts">
  import volunteerData from '../data/volunteer.json';
  import { onMount } from 'svelte';
  
  let volunteer: any[] = volunteerData;
  let mounted = false;
  
  onMount(() => {
    mounted = true;
  });
</script>

<section id="volunteering" class="mb-10">
  <div class="space-y-12 w-full py-12">
    <div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 1.3s;">
      <div class="flex flex-col items-center justify-center space-y-4 text-center">
        <div class="space-y-2">
          <div class="inline-block rounded-lg bg-foreground text-background px-3 py-1 text-sm">
            Volunteering
          </div>
          <h2 class="text-3xl font-bold tracking-tighter sm:text-5xl">
            Giving Back
          </h2>
          <p class="text-muted-foreground md:text-xl/relaxed lg:text-base/relaxed xl:text-xl/relaxed">
            I believe in using my skills to make a positive impact in the community through mentoring and open source contributions.
          </p>
        </div>
      </div>
    </div>
    <div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 1.4s;">
      <ul class="mb-4 ml-4 divide-y divide-dashed border-l">
        {#each volunteer as vol, id}
          <div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: {1.5 + id * 0.05}s;">
            <li class="relative ml-10 py-4">
              <div class="absolute -left-16 top-2 flex items-center justify-center bg-white rounded-full w-8 h-8">
                <div class="w-4 h-4 bg-foreground rounded-full"></div>
              </div>
              <div class="flex flex-1 flex-col justify-start gap-1">
                <time class="text-xs text-muted-foreground">{vol.duration}</time>
                <h3 class="font-semibold text-base">{vol.title}</h3>
                <h4 class="text-sm text-muted-foreground">{vol.organization}</h4>
                <p class="text-sm text-muted-foreground">{vol.description}</p>
                <div class="mt-2 p-3 bg-muted rounded-lg">
                  <p class="text-xs text-muted-foreground mb-1">Impact:</p>
                  <p class="text-sm font-medium">{vol.impact}</p>
                </div>
              </div>
            </li>
          </div>
        {/each}
      </ul>
    </div>
  </div>
</section>
