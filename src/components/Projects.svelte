<script lang="ts">
  import projectsData from '../data/projects.json';
  import { onMount } from 'svelte';
  
  let projects: any[] = projectsData;
  let mounted = false;
  
  onMount(() => {
    mounted = true;
  });
</script>

<section id="projects" class="mb-10">
  <div class="space-y-12 w-full py-12">
    <div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 1.1s;">
      <div class="flex flex-col items-center justify-center space-y-4 text-center">
        <div class="space-y-2">
          <div class="inline-block rounded-lg bg-foreground text-background px-3 py-1 text-sm">
            My Projects
          </div>
          <h2 class="text-3xl font-bold tracking-tighter sm:text-5xl">
            Check out my latest work
          </h2>
          <p class="text-muted-foreground md:text-xl/relaxed lg:text-base/relaxed xl:text-xl/relaxed">
            I've worked on a variety of projects, from simple websites to complex web applications. Here are a few of my favorites.
          </p>
        </div>
      </div>
    </div>
    <div class="grid grid-cols-1 gap-3 sm:grid-cols-2 max-w-[800px] mx-auto">
      {#each projects as project, id}
        <div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: {1.2 + id * 0.05}s;">
          <div class="card p-4 hover:shadow-md transition-shadow group">
            <!-- Project Image Placeholder -->
            <div class="h-40 bg-muted rounded-lg mb-4 flex items-center justify-center">
              <div class="w-16 h-16 bg-secondary rounded-lg"></div>
            </div>
            
            <div class="space-y-2">
              <div class="flex items-start justify-between">
                <h3 class="font-semibold text-base group-hover:text-muted-foreground transition-colors">
                  {project.title}
                </h3>
                {#if project.featured}
                  <span class="badge badge-secondary text-xs">
                    Featured
                  </span>
                {/if}
              </div>
              
              <p class="text-sm text-muted-foreground">
                {project.description}
              </p>
              
              <div class="flex flex-wrap gap-1">
                {#each project.technologies as tech}
                  <span class="badge badge-outline text-xs">{tech}</span>
                {/each}
              </div>
              
              <div class="flex gap-4 pt-2">
                <a 
                  href={project.github} 
                  target="_blank" 
                  rel="noopener noreferrer"
                  class="text-muted-foreground hover:text-foreground transition-colors text-sm font-medium"
                >
                  GitHub →
                </a>
                <a 
                  href={project.live} 
                  target="_blank" 
                  rel="noopener noreferrer"
                  class="text-muted-foreground hover:text-foreground transition-colors text-sm font-medium"
                >
                  Live Demo →
                </a>
              </div>
            </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>
