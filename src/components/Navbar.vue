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
      <transition
        enter-active-class="transition duration-300 ease-out"
        enter-from-class="opacity-0 translate-x-full"
        enter-to-class="opacity-100 translate-x-0"
        leave-active-class="transition duration-200 ease-in"
        leave-from-class="opacity-100 translate-x-0"
        leave-to-class="opacity-0 translate-x-full"
      >
        <div v-if="isMobileMenuOpen" class="fixed inset-0 bg-[#050203] z-[60] flex flex-col px-8 md:hidden h-screen w-screen overflow-y-auto">
          <!-- Header (Logo & Close Button) -->
          <div class="flex justify-between items-center pt-8 pb-12">
             <!-- Logo -->
             <img class="w-12 h-12" src="../assets/Image/logo 1.svg" alt="WebStack Logo">
             
             <!-- Close Button -->
             <button @click="isMobileMenuOpen = false" class="text-white hover:text-gray-300 transition-colors">
               <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                 <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
               </svg>
             </button>
          </div>

          <!-- Navigation Links -->
          <div class="flex flex-col space-y-8">
            <a 
              v-for="(link, index) in navLinks" 
              :key="link.href"
              :href="link.href" 
              @click="isMobileMenuOpen = false" 
              class="text-4xl font-bold text-white hover:text-gray-400 transition-colors"
              :class="[activeSection === link.id ? 'text-gray-200' : '']"
            >
              {{ link.label }}
            </a>
            
            <a href="#contact" @click="isMobileMenuOpen = false" class="mt-8 inline-block text-center bg-white text-black px-8 py-4 rounded-full font-bold text-lg hover:bg-gray-100 transition-colors">
              Get Started
            </a>
          </div>
        </div>
      </transition>





    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const activeSection = ref('home');
const isMobileMenuOpen = ref(false);

const navLinks = [
  { href: '#home', label: 'Home', id: 'home' },
  { href: '#about', label: 'About', id: 'about' },
  { href: '#services', label: 'Services', id: 'services' },
  { href: '#projects', label: 'Work', id: 'projects' },
  { href: '#pricing', label: 'Pricing', id: 'pricing' },
  { href: '#faq', label: 'Questions', id: 'faq' },
];

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
