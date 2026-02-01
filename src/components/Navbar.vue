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
      <button class="hidden md:block bg-black text-white px-8 py-3 rounded-full font-bold hover:bg-gray-800 transition-all duration-300 text-sm">
        Get Started
      </button>

      <!-- Mobile Menu Button -->
      <button @click="isMobileMenuOpen = !isMobileMenuOpen" class="md:hidden z-50 relative">
        <svg v-if="!isMobileMenuOpen" class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path>
        </svg>
        <svg v-else class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
        </svg>
      </button>

      <!-- Mobile Menu Overlay -->
      <div v-if="isMobileMenuOpen" class="fixed inset-0 bg-white z-40 flex flex-col items-center justify-center space-y-8 md:hidden">
        <a href="#home" @click="isMobileMenuOpen = false" class="text-2xl font-medium" :class="[activeSection === 'home' ? 'text-black' : 'text-gray-600']">Home</a>
        <a href="#about" @click="isMobileMenuOpen = false" class="text-2xl font-medium" :class="[activeSection === 'about' ? 'text-black' : 'text-gray-600']">About</a>
        <a href="#services" @click="isMobileMenuOpen = false" class="text-2xl font-medium" :class="[activeSection === 'services' ? 'text-black' : 'text-gray-600']">Services</a>
        <a href="#projects" @click="isMobileMenuOpen = false" class="text-2xl font-medium" :class="[activeSection === 'projects' ? 'text-black' : 'text-gray-600']">Work</a>
        <a href="#pricing" @click="isMobileMenuOpen = false" class="text-2xl font-medium" :class="[activeSection === 'pricing' ? 'text-black' : 'text-gray-600']">Pricing</a>
        <a href="#faq" @click="isMobileMenuOpen = false" class="text-2xl font-medium" :class="[activeSection === 'faq' ? 'text-black' : 'text-gray-600']">Questions</a>
        <button class="bg-black text-white px-8 py-3 rounded-full font-bold text-lg">
          Get Started
        </button>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const activeSection = ref('home');
const isMobileMenuOpen = ref(false);

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
