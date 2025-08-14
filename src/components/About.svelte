<script lang="ts">
  let mounted = false;
  
  import { onMount } from 'svelte';
  
  onMount(() => {
    mounted = true;
  });
</script>

<section id="about" class="mb-10">
  <div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 0.3s;">
    <h2 class="text-xl font-bold mb-3">About</h2>
  </div>
  <div class={`fade-in ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 0.4s;">
    <div class="prose max-w-full text-pretty font-sans text-sm text-muted-foreground">
      <p>
        I'm a certified TensorFlow ML Engineer, and have publications at the SciPyConf. 
        I'm passionate about building scalable machine learning solutions and contributing 
        to the open source community.
      </p>
      <p>
        When I'm not coding, you can find me writing research papers, mentoring aspiring 
        developers, or exploring the latest in AI and machine learning technologies. 
        I believe in creating technology that makes a positive impact on society.
      </p>
    </div>
  </div>
</section>
