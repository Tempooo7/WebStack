<template>
  <nav class="sticky top-0 z-50 w-full bg-white/90 backdrop-blur-md py-6 border-b border-gray-100">
    <div class="container mx-auto px-6 flex justify-between items-center text-black">
      <!-- Logo -->
      <div class="flex items-center gap-3">
        <a href="#home"><img class="w-48" src="../assets/Image/Frame 35.svg" alt="WebStack Technology Logo"></a>
      </div>
      
      <!-- Desktop Nav Links -->
      <div class="hidden md:flex items-center space-x-8 font-medium text-sm">
        <a href="#home" :class="[activeSection === 'home' ? 'border-b-2 border-black pb-1 text-black' : 'text-gray-600 hover:text-black']" class="transition-all duration-300">Home</a>
        <a href="#about" :class="[activeSection === 'about' ? 'border-b-2 border-black pb-1 text-black' : 'text-gray-600 hover:text-black']" class="transition-all duration-300">About</a>
        <a href="#services" :class="[activeSection === 'services' ? 'border-b-2 border-black pb-1 text-black' : 'text-gray-600 hover:text-black']" class="transition-all duration-300">Services</a>
        <a href="#projects" :class="[activeSection === 'projects' ? 'border-b-2 border-black pb-1 text-black' : 'text-gray-600 hover:text-black']" class="transition-all duration-300">Work</a>
        <a href="#pricing" :class="[activeSection === 'pricing' ? 'border-b-2 border-black pb-1 text-black' : 'text-gray-600 hover:text-black']" class="transition-all duration-300">Pricing</a>
        <a href="#faq" :class="[activeSection === 'faq' ? 'border-b-2 border-black pb-1 text-black' : 'text-gray-600 hover:text-black']" class="transition-all duration-300">Questions</a>
      </div>

      <!-- Desktop Button -->
      <a href="#contact" class="hidden md:block bg-black text-white px-8 py-3 rounded-full font-bold hover:bg-gray-800 transition-all duration-300 text-sm">
        Get Started
      </a>





    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const activeSection = ref('home');

const handleScroll = () => {
  const sections = ['home', 'about', 'services', 'projects', 'pricing', 'faq'];
  
  for (const section of sections) {
    const element = document.getElementById(section);
    if (element) {
      const rect = element.getBoundingClientRect();
      // Check if the section is comfortably within the viewport (top third)
      if (rect.top >= -200 && rect.top <= 300) {
        activeSection.value = section;
        break; 
      }
    }
  }
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
  // Initial check
  handleScroll();
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>
