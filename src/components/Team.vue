<template>
  <section id="team" class="py-6 px-4 text-white fade-in-section">
    <div class="container mx-auto relative bg-[#050203] text-white rounded-[40px] overflow-hidden min-h-[85vh] flex flex-col justify-between p-8 md:p-16">
      <div class="grid md:grid-cols-2 gap-16 items-center">
        <!-- Left: Heading and Description -->
        <div class="flex flex-col justify-center space-y-8">
          <div class="flex justify-between items-center">
            <h2 class="text-4xl md:text-6xl font-bold relative md:bottom-[260px]">Our Team Experts</h2>
          </div>
          
          <p class="text-2xl text-gray-300 leading-relaxed text-center max-w-md mx-auto">
            A multidisciplinary team focused on building meaningful digital experiences.
          </p>
        </div>

        <!-- Right: Team Grid -->
        <div class="relative pt-[16px] md:mt-32">
          <!-- Badge -->
          <div class="absolute -top-8 md:-top-16 right-0 flex items-center gap-2 text-sm font-medium">
            <div class="w-3 h-3 bg-white rounded-full"></div>
            <h2 class="text-base font-semibold text-white">Team Members</h2>
          </div>

          <!-- Team Grid -->
          <div class="grid grid-cols-2 gap-4">
            <div 
              v-for="(member, index) in teamMembers" 
              :key="index"
              :class="[
                'relative group overflow-hidden rounded-2xl aspect-3/4 bg-gray-800',
                index === 2 ? 'col-span-2 w-1/2 mx-auto' : ''
              ]"
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
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';
import Tamer from '../assets/Image/BookHaven.jpg'
import Mojtaba from '../assets/Image/ERP.jpg'
import Faraj from '../assets/Image/rahlaty.svg'

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
