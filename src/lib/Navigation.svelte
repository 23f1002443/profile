<script>
  import { onMount } from 'svelte';
  import { fade, fly } from 'svelte/transition';

  let mounted = false;
  let isMenuOpen = false;
  let isScrolled = false;

  const navItems = [
    { name: 'Home', href: '/' },
    { name: 'About', href: '#about' },
    { name: 'Projects', href: '#projects' },
    { name: 'Contact', href: '#contact' }
  ];

  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }

  function closeMenu() {
    isMenuOpen = false;
  }

  function handleScroll() {
    isScrolled = window.scrollY > 50;
  }

  onMount(() => {
    mounted = true;
    window.addEventListener('scroll', handleScroll);
    
    return () => {
      window.removeEventListener('scroll', handleScroll);
    };
  });
</script>

{#if mounted}
  <nav 
    class="fixed top-0 left-0 right-0 z-50 transition-all duration-300 {isScrolled ? 'bg-white/95 backdrop-blur-md shadow-lg' : 'bg-transparent'}"
    in:fade={{ duration: 500 }}
  >
    <div class="container mx-auto px-4">
      <div class="flex items-center justify-between h-16">
        <!-- Logo -->
        <div class="flex-shrink-0">
          <a href="/" class="text-2xl font-bold {isScrolled ? 'text-gray-800' : 'text-white'}">
            Portfolio
          </a>
        </div>

        <!-- Desktop Navigation -->
        <div class="hidden md:block">
          <div class="ml-10 flex items-baseline space-x-8">
            {#each navItems as item}
              <a
                href={item.href}
                class="px-3 py-2 text-sm font-medium transition-colors hover:scale-105 transform transition-transform {isScrolled ? 'text-gray-700 hover:text-blue-600' : 'text-white/90 hover:text-white'}"
                on:click={closeMenu}
              >
                {item.name}
              </a>
            {/each}
          </div>
        </div>

        <!-- Mobile menu button -->
        <div class="md:hidden">
          <button
            on:click={toggleMenu}
            class="inline-flex items-center justify-center p-2 rounded-md {isScrolled ? 'text-gray-700 hover:text-blue-600' : 'text-white hover:text-gray-300'} focus:outline-none"
          >
            <svg class="h-6 w-6" stroke="currentColor" fill="none" viewBox="0 0 24 24">
              {#if isMenuOpen}
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
              {:else}
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
              {/if}
            </svg>
          </button>
        </div>
      </div>

      <!-- Mobile Navigation Menu -->
      {#if isMenuOpen}
        <div 
          class="md:hidden bg-white border-t border-gray-200"
          in:fly={{ y: -20, duration: 300 }}
          out:fly={{ y: -20, duration: 200 }}
        >
          <div class="px-2 pt-2 pb-3 space-y-1">
            {#each navItems as item}
              <a
                href={item.href}
                class="block px-3 py-2 text-base font-medium text-gray-700 hover:text-blue-600 hover:bg-gray-50 rounded-md transition-colors"
                on:click={closeMenu}
              >
                {item.name}
              </a>
            {/each}
          </div>
        </div>
      {/if}
    </div>
  </nav>
{/if}
