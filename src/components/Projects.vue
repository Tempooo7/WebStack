<template>
  <section id="projects" class="py-6 px-4 text-white fade-in-section">
    <div class="container mx-auto relative bg-[#050203] text-white rounded-[40px] overflow-hidden min-h-[85vh] flex flex-col justify-between p-8 md:p-16">
      <!-- Header -->
      <div class="flex justify-between items-center mb-16">
        <h2 class="text-4xl md:text-6xl font-bold">Latest Projects</h2>
        <div class="flex items-center gap-2 text-sm font-medium">
          <div class="w-3 h-3 bg-white rounded-full"></div>
          <h2 class="text-base font-semibold text-white">Projects</h2>
        </div>
      </div>

      <!-- Project Card -->
      <div class="bg-white text-gray-900 rounded-3xl p-8 md:p-12">
        <div class="grid md:grid-cols-2 gap-12 items-center">
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
            <h3 class="text-3xl md:text-5xl font-bold">{{ currentProject.title }}</h3>

            <!-- Project Description -->
            <p class="text-gray-700 leading-relaxed">
              {{ currentProject.description }}
            </p>

            <!-- View Case Study Button -->
            <button class="inline-flex items-center gap-3 border-2 border-gray-900 rounded-full px-8 py-4 font-bold hover:bg-gray-900 hover:text-white transition-colors group">
              <span>VIEW CASE STUDY</span>
              <svg class="w-5 h-5 group-hover:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"></path>
              </svg>
            </button>

            <!-- Navigation Buttons -->
            <div class="flex gap-4 pt-8">
              <button 
                @click="previousProject"
                :disabled="currentProjectIndex === 0"
                :class="[
                  'px-8 py-4 rounded-full font-bold transition-all flex items-center gap-2',
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
                  'px-8 py-4 rounded-full font-bold transition-all flex items-center gap-2',
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
          <div class="relative">
            <transition name="fade" mode="out-in">
              <img 
                :key="currentProject.id"
                :src="currentProject.image" 
                :alt="currentProject.title"
                class="rounded-2xl w-full h-[400px] md:h-[500px] object-cover shadow-2xl"
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
import paySwiftImg from '../assets/Image/TempoLAP.jpg'


const currentProjectIndex = ref(0);

const projects = [
  {
    id: 1,
    year: '2025',
    category: 'E-commerce',
    type: 'Web design',
    title: 'BookHaven',
    description: 'BookHaven is a UI/UX design project centered around creating a calm, intuitive, and visually engaging experience for book discovery. The design prioritizes clarity, readability, and effortless navigation, allowing users to browse books and authors without cognitive overload.',
    image: bookHavenImg
  },
  {
    id: 2,
    year: '2025',
    category: 'ERP Module',
    type: 'Web App',
    title: 'TemposWork',
    description: 'Tempo’s Lap is an educational UI/UX design project focused on simplifying technical learning, especially networking topics, through a clear structure, intuitive navigation, and learner-centered interactions like quizzes and progress tracking.',
    image: taskFlowProImg
  },
  {
    id: 3,
    year: '2025',
    category: 'Educational',
    type: 'Mobile App',
    title: 'Tempo’s Lap',
    description: 'Tempo’s Lap is an educational UI/UX design project focused on simplifying technical learning, especially networking topics, through a clear structure, intuitive navigation, and learner-centered interactions like quizzes and progress tracking.',
    image: paySwiftImg
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
