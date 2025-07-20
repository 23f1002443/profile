<script>
  import { onMount } from 'svelte';
  import { fade, fly } from 'svelte/transition';
  import { gsap } from 'gsap';
  import { ScrollTrigger } from 'gsap/ScrollTrigger';

  let mounted = false;
  let aboutSection;

  onMount(() => {
    mounted = true;
    gsap.registerPlugin(ScrollTrigger);

    gsap.from(aboutSection, {
      scrollTrigger: {
        trigger: aboutSection,
        start: "top 80%",
        end: "bottom 20%",
        toggleActions: "play none none none"
      },
      duration: 1,
      y: 50,
      opacity: 0,
      ease: "power3.out"
    });
  });
</script>

<section id="about" class="section-padding bg-white" bind:this={aboutSection}>
  <div class="container mx-auto max-w-6xl">
    {#if mounted}
      <div class="text-center mb-16">
        <h2 class="text-4xl md:text-5xl font-bold text-gradient mb-4">About Me</h2>
        <div class="w-24 h-1 bg-gradient-to-r from-blue-600 to-purple-600 mx-auto"></div>
      </div>

      <div class="grid md:grid-cols-2 gap-12 items-center">
        <div 
          class="text-center md:text-left"
          in:fly={{ x: -50, duration: 800, delay: 200 }}
        >
          <div class="relative inline-block mb-8">
            <!-- Profile image -->
            <img src="/monke-profile.png" alt="rise of monke profile" class="w-64 h-64 object-cover rounded-full mx-auto md:mx-0 shadow-2xl border-4 border-blue-400" />
            <!-- Decorative elements -->
            <div class="absolute -top-4 -right-4 w-8 h-8 bg-yellow-400 rounded-full animate-bounce-slow"></div>
            <div class="absolute -bottom-4 -left-4 w-6 h-6 bg-pink-400 rounded-full animate-bounce-slow" style="animation-delay: 0.5s;"></div>
          </div>
        </div>

        <div 
          class="space-y-6"
          in:fly={{ x: 50, duration: 800, delay: 400 }}
        >
          <h3 class="text-3xl font-bold text-gradient mb-4">rise of monke</h3>
          <p class="text-lg text-gray-700 leading-relaxed">
            Welcome to the rise of monke. Embracing simplicity, curiosity, and the spirit of exploration. This is my digital jungle—where ideas swing freely and creativity climbs to new heights.
          </p>
          <div class="grid grid-cols-2 gap-4 mt-8">
            <div class="bg-gray-50 p-4 rounded-lg">
              <h4 class="font-semibold text-gray-800 mb-2">Frontend</h4>
              <p class="text-sm text-gray-600">Svelte, React, Vue, TypeScript</p>
            </div>
            <div class="bg-gray-50 p-4 rounded-lg">
              <h4 class="font-semibold text-gray-800 mb-2">Backend</h4>
              <p class="text-sm text-gray-600">Node.js, Python, PostgreSQL</p>
            </div>
            <div class="bg-gray-50 p-4 rounded-lg">
              <h4 class="font-semibold text-gray-800 mb-2">Design</h4>
              <p class="text-sm text-gray-600">Figma, Tailwind CSS</p>
            </div>
            <div class="bg-gray-50 p-4 rounded-lg">
              <h4 class="font-semibold text-gray-800 mb-2">Tools</h4>
              <p class="text-sm text-gray-600">Git, Docker, Vercel</p>
            </div>
          </div>
          <div class="pt-6">
            <a href="#contact" class="btn-primary">
              Let's Work Together
            </a>
          </div>
        </div>
      </div>
    {/if}
  </div>
</section>
