<script>
  import { onMount } from 'svelte';
  import { fade, fly } from 'svelte/transition';
  import { gsap } from 'gsap';

  let mounted = false;
  let heroTitle;
  let heroSubtitle;

  onMount(() => {
    mounted = true;
    
    // GSAP animations for hero text
    gsap.from(heroTitle, {
      duration: 1.5,
      y: 50,
      opacity: 0,
      ease: "power3.out",
      delay: 0.3
    });
    
    gsap.from(heroSubtitle, {
      duration: 1.5,
      y: 30,
      opacity: 0,
      ease: "power3.out",
      delay: 0.6
    });

    // Floating animation for background elements
    gsap.to(".floating-1", {
      duration: 3,
      y: -20,
      repeat: -1,
      yoyo: true,
      ease: "power2.inOut"
    });
    
    gsap.to(".floating-2", {
      duration: 4,
      y: -30,
      repeat: -1,
      yoyo: true,
      ease: "power2.inOut",
      delay: 1
    });
  });
</script>

<section class="min-h-screen flex items-center justify-center hero-bg relative overflow-hidden">
  <!-- Animated background elements -->
  <div class="absolute inset-0 overflow-hidden">
    <div class="floating-1 absolute top-1/4 left-1/4 w-32 h-32 bg-white/10 rounded-full blur-xl"></div>
    <div class="floating-2 absolute top-3/4 right-1/4 w-48 h-48 bg-white/5 rounded-full blur-2xl"></div>
    <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-96 h-96 bg-white/5 rounded-full blur-3xl"></div>
  </div>

  <div class="container mx-auto px-4 text-center relative z-10">
    {#if mounted}
      <div bind:this={heroTitle} class="opacity-0">
        <h1 class="text-5xl md:text-7xl font-bold text-white mb-6">
          Hi, I'm <span class="text-yellow-300">rise of monke</span>
        </h1>
      </div>
      
      <div bind:this={heroSubtitle} class="opacity-0">
        <p class="text-xl md:text-2xl text-white/90 mb-8 max-w-3xl mx-auto">
          Full Stack Developer & UI/UX Designer passionate about creating amazing digital experiences
        </p>
      </div>
      
      <div 
        class="space-x-4"
        in:fly={{ y: 50, duration: 1000, delay: 900 }}
      >
        <a href="#projects" class="btn-primary inline-block">
          View My Work
        </a>
        <a 
          href="#contact" 
          class="bg-transparent border-2 border-white text-white px-8 py-3 rounded-full font-semibold transition-all duration-300 hover:bg-white hover:text-purple-600 transform hover:scale-105 inline-block"
        >
          Get In Touch
        </a>
      </div>
    {/if}
  </div>

  <!-- Scroll indicator -->
  <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
    <div class="w-6 h-10 border-2 border-white/50 rounded-full flex justify-center">
      <div class="w-1 h-3 bg-white/50 rounded-full mt-2"></div>
    </div>
  </div>
</section>
