<script>
  import { onMount } from 'svelte';
  import { fade, fly, scale } from 'svelte/transition';
  import { gsap } from 'gsap';
  import { ScrollTrigger } from 'gsap/ScrollTrigger';

  let mounted = false;
  let projectsSection;

  const projects = [
    {
      id: 1,
      title: "E-Commerce Platform",
      description: "A full-stack e-commerce solution built with React, Node.js, and PostgreSQL. Features include user authentication, payment processing, and admin dashboard.",
      image: "https://images.unsplash.com/photo-1556742049-0cfed4f6a45d?w=500&h=300&fit=crop",
      technologies: ["React", "Node.js", "PostgreSQL", "Stripe"],
      demoLink: "#",
      codeLink: "#"
    },
    {
      id: 2,
      title: "Task Management App",
      description: "A collaborative task management application with real-time updates, drag-and-drop functionality, and team collaboration features.",
      image: "https://images.unsplash.com/photo-1611224923853-80b023f02d71?w=500&h=300&fit=crop",
      technologies: ["Vue.js", "Firebase", "Vuetify", "Socket.io"],
      demoLink: "#",
      codeLink: "#"
    },
    {
      id: 3,
      title: "Weather Dashboard",
      description: "A beautiful weather dashboard with interactive maps, detailed forecasts, and location-based weather alerts using multiple APIs.",
      image: "https://images.unsplash.com/photo-1504608524841-42fe6f032b4b?w=500&h=300&fit=crop",
      technologies: ["Svelte", "D3.js", "OpenWeather API", "Mapbox"],
      demoLink: "#",
      codeLink: "#"
    },
    {
      id: 4,
      title: "Portfolio Website",
      description: "A responsive portfolio website showcasing modern design principles, smooth animations, and optimized performance.",
      image: "https://images.unsplash.com/photo-1467232004584-a241de8bcf5d?w=500&h=300&fit=crop",
      technologies: ["Svelte", "Tailwind CSS", "GSAP", "Vite"],
      demoLink: "#",
      codeLink: "#"
    }
  ];

  onMount(() => {
    mounted = true;
    gsap.registerPlugin(ScrollTrigger);

    gsap.from(projectsSection, {
      scrollTrigger: {
        trigger: projectsSection,
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

<section id="projects" class="section-padding bg-gray-50" bind:this={projectsSection}>
  <div class="container mx-auto max-w-7xl">
    {#if mounted}
      <div class="text-center mb-16">
        <h2 class="text-4xl md:text-5xl font-bold text-gradient mb-4">Featured Projects</h2>
        <div class="w-24 h-1 bg-gradient-to-r from-blue-600 to-purple-600 mx-auto mb-6"></div>
        <p class="text-xl text-gray-600 max-w-2xl mx-auto">
          Here are some of my recent projects that showcase my skills and passion for creating amazing digital experiences.
        </p>
      </div>

      <div class="grid md:grid-cols-2 lg:grid-cols-2 gap-8">
        {#each projects as project, index}
          <div 
            class="bg-white rounded-xl shadow-lg overflow-hidden card-hover"
            in:fly={{ y: 50, duration: 600, delay: index * 100 }}
          >
            <!-- Project Image -->
            <div class="relative overflow-hidden">
              <div class="w-full h-48 bg-gradient-to-br from-blue-400 to-purple-600 flex items-center justify-center text-white text-2xl font-bold">
                Project {project.id}
              </div>
              <div class="absolute inset-0 bg-gradient-to-t from-black/50 to-transparent opacity-0 hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                <div class="space-x-4">
                  <a href={project.demoLink} class="bg-white text-gray-800 px-4 py-2 rounded-lg font-semibold hover:bg-gray-100 transition-colors">
                    Live Demo
                  </a>
                  <a href={project.codeLink} class="border-2 border-white text-white px-4 py-2 rounded-lg font-semibold hover:bg-white hover:text-gray-800 transition-colors">
                    View Code
                  </a>
                </div>
              </div>
            </div>

            <!-- Project Content -->
            <div class="p-6">
              <h3 class="text-xl font-bold text-gray-800 mb-3">{project.title}</h3>
              <p class="text-gray-600 mb-4 leading-relaxed">{project.description}</p>
              
              <!-- Technologies -->
              <div class="flex flex-wrap gap-2 mb-4">
                {#each project.technologies as tech}
                  <span class="bg-blue-100 text-blue-800 px-3 py-1 rounded-full text-sm font-medium">
                    {tech}
                  </span>
                {/each}
              </div>

              <!-- Action Buttons -->
              <div class="flex space-x-4">
                <a href={project.demoLink} class="flex-1 bg-gradient-to-r from-blue-600 to-purple-600 text-white px-4 py-2 rounded-lg font-semibold text-center hover:shadow-lg transition-shadow">
                  Live Demo
                </a>
                <a href={project.codeLink} class="flex-1 border-2 border-gray-300 text-gray-700 px-4 py-2 rounded-lg font-semibold text-center hover:border-gray-400 transition-colors">
                  View Code
                </a>
              </div>
            </div>
          </div>
        {/each}
      </div>

      <div class="text-center mt-12">
        <a href="/projects" class="btn-primary">
          View All Projects
        </a>
      </div>
    {/if}
  </div>
</section>
