<template>
  <section id="projects" class="py-6 px-4 text-white fade-in-section scroll-mt-32">
    <div class="container mx-auto relative bg-[#050203] text-white rounded-[40px] overflow-hidden min-h-[85vh] flex flex-col justify-between p-4 md:p-16">
      <!-- Header -->
      <div class="flex justify-between items-center mb-8 md:mb-16">
        <h2 class="text-3xl md:text-6xl font-bold">Latest Projects</h2>
        <div class="flex items-center gap-2 text-sm font-medium">
          <div class="w-3 h-3 bg-white rounded-full"></div>
          <h2 class="text-base font-semibold text-white">Projects</h2>
        </div>
      </div>

      <!-- Project Card -->
      <div class="bg-white text-gray-900 rounded-3xl p-6 md:p-12">
        <div class="flex flex-col-reverse md:grid md:grid-cols-2 gap-6 md:gap-12 items-center">
          <!-- Left: Project Details -->
          <div class="space-y-6">
            <!-- Project Number -->
            <div class="inline-block border-2 border-gray-900 rounded-full px-6 py-2">
              <span class="font-bold">{{ String(currentProjectIndex + 1).padStart(2, '0') }}</span>
            </div>

            <!-- Project Meta -->
            <div class="text-sm text-gray-600 font-medium">
              {{ currentProject.year }} . {{ currentProject.category }} . {{ currentProject.type }}
            </div>

            <!-- Project Title -->
            <h3 class="text-2xl md:text-5xl font-bold">{{ currentProject.title }}</h3>

            <!-- Project Description -->
            <p class="text-sm md:text-base text-gray-700 leading-relaxed">
              {{ currentProject.description }}
            </p>

            <!-- View Case Study Button -->
            <a 
              :href="currentProject.link" 
              target="_blank"
              class="inline-flex items-center gap-3 border-2 border-gray-900 rounded-full px-6 py-3 md:px-8 md:py-4 font-bold hover:bg-gray-900 hover:text-white transition-colors group text-sm md:text-base"
            >
              <span>VIEW CASE STUDY</span>
              <svg class="w-4 h-4 md:w-5 md:h-5 group-hover:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"></path>
              </svg>
            </a>

            <!-- Navigation Buttons -->
            <div class="flex gap-3 pt-6 md:pt-8">
              <button 
                @click="previousProject"
                :disabled="currentProjectIndex === 0"
                :class="[
                  'px-6 py-3 md:px-8 md:py-4 rounded-full font-bold transition-all flex items-center gap-2 text-sm md:text-base',
                  currentProjectIndex === 0 
                    ? 'bg-gray-300 text-gray-500 cursor-not-allowed' 
                    : 'bg-black text-white hover:bg-gray-800'
                ]"
              >
                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"></path>
                </svg>
                PREVIOUS
              </button>
              <button 
                @click="nextProject"
                :disabled="currentProjectIndex === projects.length - 1"
                :class="[
                  'px-6 py-3 md:px-8 md:py-4 rounded-full font-bold transition-all flex items-center gap-2 text-sm md:text-base',
                  currentProjectIndex === projects.length - 1
                    ? 'border-2 border-gray-300 text-gray-400 cursor-not-allowed'
                    : 'border-2 border-gray-900 hover:bg-gray-900 hover:text-white'
                ]"
              >
                NEXT
                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path>
                </svg>
              </button>
            </div>
          </div>

          <!-- Right: Project Image -->
          <div class="relative w-full">
            <transition name="fade" mode="out-in">
              <img 
                :key="currentProject.id"
                :src="currentProject.image" 
                :alt="currentProject.title"
                class="rounded-2xl w-full h-[200px] md:h-[500px] object-cover shadow-2xl"
              >
            </transition>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue';
import bookHavenImg from '../assets/Image/BookHaven.jpg'
import taskFlowProImg from '../assets/Image/ERP.jpg'
import paySwiftImg from '../assets/Image/rahlaty.svg'


const currentProjectIndex = ref(0);

const projects = [
  {
    id: 1,
    year: '2025',
    category: 'E-commerce',
    type: 'Web design',
    title: 'BookHaven',
    description: 'BookHaven is a front-end web project designed as a modern and user-friendly landing page for an online book discovery platform. The project focuses on presenting books in a clean, visually appealing way while emphasizing usability, clarity, and smooth user experience.',
    image: bookHavenImg,
    link: 'https://tempooo7.github.io/Book-Haven/'
  },
  {
    id: 2,
    year: '2025',
    category: 'ERP Module',
    type: 'Web App',
    title: 'TemposWork',
    description: 'Tempo’s Lap is an educational UI/UX design project focused on simplifying technical learning, especially networking topics, through a clear structure, intuitive navigation, and learner-centered interactions like quizzes and progress tracking.',
    image: taskFlowProImg,
    link: 'https://www.behance.net/gallery/237000593/Inventory-Management-Module-(ERP)'
  },
  {
    id: 3,
    year: '2025',
    category: 'Educational',
    type: 'Mobile App',
    title: 'Rahlaty',
    description: 'Rahlaty is a UI/UX design project focused on creating a smooth and engaging travel experience from discovery to planning. The project emphasizes clear navigation, visual storytelling, and user-friendly flows that help users explore destinations, organize trips, and make decisions with ease. The overall design balances aesthetics with usability to make travel planning feel simple and enjoyable.',
    image: paySwiftImg,
    link: 'https://www.behance.net/gallery/233103071/Rahlaty'
  }
];

const currentProject = computed(() => projects[currentProjectIndex.value]);

const nextProject = () => {
  if (currentProjectIndex.value < projects.length - 1) {
    currentProjectIndex.value++;
  }
};

const previousProject = () => {
  if (currentProjectIndex.value > 0) {
    currentProjectIndex.value--;
  }
};
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
