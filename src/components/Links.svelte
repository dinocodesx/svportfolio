<script lang="ts">
  import linksData from '../data/links.json';
  
  let links: any[] = linksData;
  
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

<section id="links" class="py-20">
  <div class="max-w-4xl mx-auto">
    <h2 class="text-4xl font-bold text-white mb-12 text-center">Connect With Me</h2>
    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
      {#each links as link}
        <a 
          href={link.url}
          target="_blank"
          rel="noopener noreferrer"
          class="bg-gray-900 rounded-2xl p-6 border border-gray-800 hover:border-gray-600 transition-all group hover:bg-gray-800"
        >
          <div class="flex items-center mb-3">
            <span class="text-2xl mr-3">{getIcon(link.icon)}</span>
            <h3 class="text-lg font-semibold text-white group-hover:text-gray-300 transition-colors">
              {link.name}
            </h3>
          </div>
          <p class="text-gray-400 text-sm">
            {link.description}
          </p>
        </a>
      {/each}
    </div>
  </div>
</section>
