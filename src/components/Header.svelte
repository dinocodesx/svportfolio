<script lang="ts">
  let isMenuOpen = false;
  
  const navItems = [
    { href: '#about', label: 'About' },
    { href: '#skills', label: 'Skills' },
    { href: '#experience', label: 'Experience' },
    { href: '#projects', label: 'Projects' },
    { href: '#volunteering', label: 'Volunteering' },
    { href: '#blogs', label: 'Blogs' },
    { href: '#links', label: 'Connect' }
  ];
  
  function scrollToSection(href: string) {
    isMenuOpen = false;
    const element = document.querySelector(href);
    if (element) {
      element.scrollIntoView({ behavior: 'smooth' });
    }
  }
</script>

<header class="fixed top-0 left-0 right-0 z-50 bg-black/90 backdrop-blur-sm border-b border-gray-800">
  <nav class="max-w-7xl mx-auto px-8 lg:px-20">
    <div class="flex justify-between items-center h-16">
      <!-- Logo -->
      <div class="flex items-center">
        <span class="text-white text-xl font-bold">Portfolio</span>
      </div>
      
      <!-- Desktop Navigation -->
      <div class="hidden md:flex items-center space-x-8">
        {#each navItems as item}
          <button
            on:click={() => scrollToSection(item.href)}
            class="text-gray-400 hover:text-white transition-colors text-sm font-medium"
          >
            {item.label}
          </button>
        {/each}
      </div>
      
      <!-- Mobile Menu Button -->
      <button
        class="md:hidden text-white"
        on:click={() => isMenuOpen = !isMenuOpen}
      >
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          {#if isMenuOpen}
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
          {:else}
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
          {/if}
        </svg>
      </button>
    </div>
    
    <!-- Mobile Navigation -->
    {#if isMenuOpen}
      <div class="md:hidden bg-black/95 border-t border-gray-800">
        <div class="px-2 pt-2 pb-3 space-y-1">
          {#each navItems as item}
            <button
              on:click={() => scrollToSection(item.href)}
              class="block w-full text-left px-3 py-2 text-gray-400 hover:text-white transition-colors"
            >
              {item.label}
            </button>
          {/each}
        </div>
      </div>
    {/if}
  </nav>
</header>
