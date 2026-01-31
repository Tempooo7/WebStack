<template>
  <section id="team" class="py-6 px-4 text-white">
    <div class="container mx-auto relative bg-[#050203] text-white rounded-[40px] overflow-hidden min-h-[85vh] flex flex-col justify-between p-8 md:p-16">
      <div class="grid md:grid-cols-2 gap-16 items-center">
        <!-- Left: Heading and Description -->
        <div class="flex flex-col justify-center space-y-8">
          <div class="flex justify-between items-center">
            <h2 class="text-6xl font-bold relative bottom-[230px]">Our Team Experts</h2>
          </div>
          
          <p class="text-2xl text-gray-300 leading-relaxed text-center max-w-md mx-auto">
            A multidisciplinary team focused on building meaningful digital experiences.
          </p>
        </div>

        <!-- Right: Team Grid -->
        <div class="relative pt-[16px]">
          <!-- Badge -->
          <div class="absolute -top-8 right-0 flex items-center gap-2 text-sm font-medium">
            <div class="w-3 h-3 bg-white rounded-full"></div>
            <h2 class="text-base font-semibold text-white">Team Members</h2>
          </div>

          <!-- Team Grid -->
          <div class="grid grid-cols-2 gap-4">
            <div 
              v-for="(member, index) in teamMembers" 
              :key="index"
              class="relative group overflow-hidden rounded-2xl aspect-[3/4] bg-gray-800"
            >
              <img 
                :src="member.image" 
                :alt="member.name"
                class="w-full h-full object-cover"
              >
              
              <!-- Hover Overlay -->
              <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex flex-col justify-end p-6">
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

const teamMembers = ref([
  {
    name: 'John Smith',
    role: 'Lead Designer',
    image: 'https://images.unsplash.com/photo-1560250097-0b93528c311a?w=400&h=600&fit=crop'
  },
  {
    name: 'Sarah Johnson',
    role: 'Frontend Developer',
    image: 'https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?w=400&h=600&fit=crop'
  },
  {
    name: 'Emily Davis',
    role: 'UX Designer',
    image: 'https://images.unsplash.com/photo-1580489944761-15a19d654956?w=400&h=600&fit=crop'
  },
  {
    name: 'Michael Brown',
    role: 'Developer',
    image: 'https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=400&h=600&fit=crop'
  }
]);
</script>
