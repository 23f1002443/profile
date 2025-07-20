<script>
  import { onMount } from 'svelte';
  import { fade, fly } from 'svelte/transition';
  import { gsap } from 'gsap';
  import { ScrollTrigger } from 'gsap/ScrollTrigger';

  let mounted = false;
  let contactSection;
  let form;

  const socialLinks = [
    { name: 'GitHub', url: 'https://github.com', icon: '💻' },
    { name: 'LinkedIn', url: 'https://linkedin.com', icon: '💼' },
    { name: 'Twitter', url: 'https://twitter.com', icon: '🐦' },
    { name: 'Email', url: 'mailto:your.email@example.com', icon: '📧' }
  ];

  let formData = {
    name: '',
    email: '',
    message: ''
  };

  function handleSubmit(event) {
    event.preventDefault();
    // Handle form submission here
    console.log('Form submitted:', formData);
    // You can add actual form submission logic here
    alert('Thank you for your message! I\'ll get back to you soon.');
    
    // Reset form
    formData = { name: '', email: '', message: '' };
  }

  onMount(() => {
    mounted = true;
    gsap.registerPlugin(ScrollTrigger);

    gsap.from(contactSection, {
      scrollTrigger: {
        trigger: contactSection,
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

<section id="contact" class="section-padding bg-white" bind:this={contactSection}>
  <div class="container mx-auto max-w-4xl">
    {#if mounted}
      <div class="text-center mb-16">
        <h2 class="text-4xl md:text-5xl font-bold text-gradient mb-4">Get In Touch</h2>
        <div class="w-24 h-1 bg-gradient-to-r from-blue-600 to-purple-600 mx-auto mb-6"></div>
        <p class="text-xl text-gray-600 max-w-2xl mx-auto">
          I'm always interested in hearing about new opportunities and interesting projects. Let's create something amazing together!
        </p>
      </div>

      <div class="grid md:grid-cols-2 gap-12">
        <!-- Contact Info -->
        <div 
          class="space-y-8"
          in:fly={{ x: -50, duration: 800, delay: 200 }}
        >
          <div>
            <h3 class="text-2xl font-bold text-gray-800 mb-6">Let's Connect</h3>
            <p class="text-gray-600 leading-relaxed mb-8">
              Whether you have a project in mind, want to collaborate, or just want to say hello, I'd love to hear from you. Drop me a message and I'll get back to you as soon as possible!
            </p>
          </div>

          <!-- Contact Details -->
          <div class="space-y-4">
            <div class="flex items-center space-x-4">
              <div class="w-12 h-12 bg-gradient-to-r from-blue-600 to-purple-600 rounded-full flex items-center justify-center text-white text-xl">
                📧
              </div>
              <div>
                <h4 class="font-semibold text-gray-800">Email</h4>
                <p class="text-gray-600">your.email@example.com</p>
              </div>
            </div>
            
            <div class="flex items-center space-x-4">
              <div class="w-12 h-12 bg-gradient-to-r from-blue-600 to-purple-600 rounded-full flex items-center justify-center text-white text-xl">
                📱
              </div>
              <div>
                <h4 class="font-semibold text-gray-800">Phone</h4>
                <p class="text-gray-600">+1 (555) 123-4567</p>
              </div>
            </div>
            
            <div class="flex items-center space-x-4">
              <div class="w-12 h-12 bg-gradient-to-r from-blue-600 to-purple-600 rounded-full flex items-center justify-center text-white text-xl">
                📍
              </div>
              <div>
                <h4 class="font-semibold text-gray-800">Location</h4>
                <p class="text-gray-600">San Francisco, CA</p>
              </div>
            </div>
          </div>

          <!-- Social Links -->
          <div>
            <h4 class="font-semibold text-gray-800 mb-4">Follow Me</h4>
            <div class="flex space-x-4">
              {#each socialLinks as social}
                <a 
                  href={social.url}
                  class="w-12 h-12 bg-gray-100 rounded-full flex items-center justify-center text-xl hover:bg-gradient-to-r hover:from-blue-600 hover:to-purple-600 hover:text-white transition-all duration-300 transform hover:scale-110"
                  target="_blank"
                  rel="noopener noreferrer"
                  title={social.name}
                >
                  {social.icon}
                </a>
              {/each}
            </div>
          </div>
        </div>

        <!-- Contact Form -->
        <div 
          class="bg-gray-50 p-8 rounded-xl"
          in:fly={{ x: 50, duration: 800, delay: 400 }}
        >
          <form on:submit={handleSubmit} bind:this={form} class="space-y-6">
            <div>
              <label for="name" class="block text-sm font-semibold text-gray-700 mb-2">Name</label>
              <input
                type="text"
                id="name"
                bind:value={formData.name}
                required
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-colors"
                placeholder="Your full name"
              />
            </div>

            <div>
              <label for="email" class="block text-sm font-semibold text-gray-700 mb-2">Email</label>
              <input
                type="email"
                id="email"
                bind:value={formData.email}
                required
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-colors"
                placeholder="your.email@example.com"
              />
            </div>

            <div>
              <label for="message" class="block text-sm font-semibold text-gray-700 mb-2">Message</label>
              <textarea
                id="message"
                bind:value={formData.message}
                required
                rows="5"
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent transition-colors resize-none"
                placeholder="Tell me about your project or just say hello!"
              ></textarea>
            </div>

            <button
              type="submit"
              class="w-full btn-primary"
            >
              Send Message
            </button>
          </form>
        </div>
      </div>
    {/if}
  </div>
</section>
