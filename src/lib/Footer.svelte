<script>
  const currentYear = new Date().getFullYear();
  
  const socialLinks = [
    { name: 'GitHub', url: 'https://github.com', icon: '💻' },
    { name: 'LinkedIn', url: 'https://linkedin.com', icon: '💼' },
    { name: 'Twitter', url: 'https://twitter.com', icon: '🐦' },
    { name: 'Email', url: 'mailto:your.email@example.com', icon: '📧' }
  ];
</script>

<footer class="bg-gray-900 text-white py-12">
  <div class="container mx-auto px-4">
    <div class="grid md:grid-cols-3 gap-8">
      <!-- Brand -->
      <div class="col-span-1">
        <h3 class="text-2xl font-bold mb-4">rise of monke</h3>
        <p class="text-gray-400 leading-relaxed">
          Full Stack Developer passionate about creating amazing digital experiences and bringing ideas to life through code.
        </p>
      </div>

      <!-- Quick Links -->
      <div class="col-span-1">
        <h4 class="text-lg font-semibold mb-4">Quick Links</h4>
        <ul class="space-y-2">
          <li><a href="#about" class="text-gray-400 hover:text-white transition-colors">About</a></li>
          <li><a href="#projects" class="text-gray-400 hover:text-white transition-colors">Projects</a></li>
          <li><a href="#contact" class="text-gray-400 hover:text-white transition-colors">Contact</a></li>
          <li><a href="/resume.pdf" class="text-gray-400 hover:text-white transition-colors">Resume</a></li>
        </ul>
      </div>

      <!-- Contact & Social -->
      <div class="col-span-1">
        <h4 class="text-lg font-semibold mb-4">Get In Touch</h4>
        <p class="text-gray-400 mb-4">your.email@example.com</p>
        <div class="flex space-x-4">
          {#each socialLinks as social}
            <a 
              href={social.url}
              class="w-10 h-10 bg-gray-800 rounded-full flex items-center justify-center hover:bg-gradient-to-r hover:from-blue-600 hover:to-purple-600 transition-all duration-300 transform hover:scale-110"
              target="_blank"
              rel="noopener noreferrer"
              title={social.name}
            >
              <span class="text-sm">{social.icon}</span>
            </a>
          {/each}
        </div>
      </div>
    </div>

    <!-- Bottom Bar -->
    <div class="border-t border-gray-800 mt-8 pt-8 text-center">
      <p class="text-gray-400">
        © {currentYear} rise of monke. All rights reserved. Built with ❤️ using Svelte & Tailwind CSS.
      </p>
    </div>
  </div>
</footer>
