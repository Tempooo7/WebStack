<template>
  <section id="team" class="py-6 px-4 text-white fade-in-section">
    <div class="container mx-auto relative bg-[#050203] text-white rounded-[40px] overflow-hidden min-h-[85vh] flex flex-col items-center p-8 md:p-16">
      
      <!-- Top corners -->
      <h2 class="absolute top-8 left-8 md:top-16 md:left-16 text-2xl md:text-5xl font-bold">Our Team Experts</h2>
      
      <div class="absolute top-8 right-8 md:top-16 md:right-16 flex items-center gap-2 text-sm font-medium">
        <div class="w-3 h-3 bg-white rounded-full"></div>
        <h2 class="text-base font-semibold text-white">Team Members</h2>
      </div>

      <!-- Center Content -->
      <div class="flex flex-col items-center text-center space-y-6 mt-24 md:mt-32 mb-12 max-w-3xl z-10">
        <p class="text-2xl text-gray-300 leading-relaxed">
          A multidisciplinary team focused on building meaningful digital experiences.
        </p>
      </div>

      <!-- Team Grid -->
      <div class="relative w-full max-w-6xl">
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8 place-items-center">
          <div 
            v-for="(member, index) in teamMembers" 
            :key="index"
            class="relative group overflow-hidden rounded-2xl aspect-4/5 w-full max-w-[280px] bg-gray-800"
          >
            <img 
              :src="member.image" 
              :alt="member.name"
              class="w-full h-full object-cover"
            >
            
            <!-- Hover Overlay -->
            <div class="absolute inset-0 bg-linear-to-t from-black/80 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex flex-col justify-end p-6">
              <div class="text-white">
                <div class="font-bold text-lg">{{ member.role }}</div>
                <div class="text-sm opacity-90">{{ member.name }}</div>
              </div>
            </div>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';
import Tamer from '../assets/Image/Tamer.jpg'
import Mojtaba from '../assets/Image/Mojtaba.jpg'
import Faraj from '../assets/Image/Faraj.jpg'

const teamMembers = ref([
  {
    name: 'Tamer Mohammed',
    role: 'Founder',
    image: Tamer
  },
  {
    name: 'Mojtaba Ahmed',
    role: 'Founder',
    image: Mojtaba
  },
  {
    name: 'Faraj Rm',
    role: 'Founder',
    image: Faraj
  },
 
]);
</script>
