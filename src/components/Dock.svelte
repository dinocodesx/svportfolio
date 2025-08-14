<script lang="ts">
  import { onMount } from 'svelte';
  
  let mounted = false;
  
  const navItems = [
    { href: '#hero', icon: '🏠', label: 'Home' },
    { href: '#about', icon: '👤', label: 'About' },
    { href: '#work', icon: '💼', label: 'Work' },
    { href: '#skills', icon: '🛠️', label: 'Skills' },
    { href: '#projects', icon: '🚀', label: 'Projects' },
    { href: '#volunteering', icon: '🤝', label: 'Volunteering' },
    { href: '#contact', icon: '📧', label: 'Contact' }
  ];
  
  const socialLinks = [
    { href: 'https://github.com/username', icon: '🐙', label: 'GitHub' },
    { href: 'https://linkedin.com/in/username', icon: '💼', label: 'LinkedIn' },
    { href: 'https://twitter.com/username', icon: '🐦', label: 'Twitter' }
  ];
  
  function scrollToSection(href: string) {
    const element = document.querySelector(href);
    if (element) {
      element.scrollIntoView({ behavior: 'smooth' });
    }
  }
  
  onMount(() => {
    mounted = true;
  });
</script>

<div class="pointer-events-none fixed inset-x-0 bottom-0 z-30 mx-auto mb-4 flex origin-bottom h-full max-h-14">
  <div class="fixed bottom-0 inset-x-0 h-16 w-full bg-background to-transparent backdrop-blur-lg"></div>
  <div class={`z-50 pointer-events-auto relative mx-auto flex min-h-full h-full items-center px-1 bg-background rounded-full border border-border shadow-lg ${mounted ? 'opacity-100' : 'opacity-0'}`} style="animation-delay: 2s;">
    <!-- Navigation items -->
    {#each navItems as item}
      <button
        on:click={() => scrollToSection(item.href)}
        class="size-12 flex items-center justify-center hover:bg-muted rounded-full transition-colors group relative"
        title={item.label}
      >
        <span class="text-lg">{item.icon}</span>
        <div class="absolute bottom-full mb-2 px-2 py-1 bg-foreground text-background text-xs rounded opacity-0 group-hover:opacity-100 transition-opacity pointer-events-none whitespace-nowrap">
          {item.label}
        </div>
      </button>
    {/each}
    
    <!-- Separator -->
    <div class="h-8 w-px bg-border mx-1"></div>
    
    <!-- Social links -->
    {#each socialLinks as social}
      <a
        href={social.href}
        target="_blank"
        rel="noopener noreferrer"
        class="size-12 flex items-center justify-center hover:bg-muted rounded-full transition-colors group relative"
        title={social.label}
      >
        <span class="text-lg">{social.icon}</span>
        <div class="absolute bottom-full mb-2 px-2 py-1 bg-foreground text-background text-xs rounded opacity-0 group-hover:opacity-100 transition-opacity pointer-events-none whitespace-nowrap">
          {social.label}
        </div>
      </a>
    {/each}
  </div>
</div>
