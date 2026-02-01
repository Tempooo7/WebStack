<template>
  <section id="services" class="py-6 px-4 fade-in-section">
    <div class="container mx-auto relative bg-[#F7F7F7] text-white rounded-[40px] overflow-hidden min-h-[85vh] flex flex-col justify-between p-8 md:p-16">
      <!-- Header -->
      <div class="flex justify-between items-center mb-16">
        <h2 class="text-6xl font-bold text-gray-900">Services</h2>
        
        <!-- Navigation Dots -->
        <div class="hidden md:flex items-center gap-8 text-2xl text-gray-400">
       <div class="flex items-center gap-3 mb-8">
          <span>+</span>
          <span>×</span>
          <span>×</span>
          </div>
          <div class="flex items-center gap-3 mb-8">
        <div class="w-3 h-3 bg-black rounded-full"></div>
        <h2 class="text-base font-semibold text-black">Services</h2>
      </div>
        </div>
      </div>

      <!-- Services List -->
      <div class="space-y-0">
        <!-- Service Item -->
        <div 
          v-for="(service, index) in services" 
          :key="service.id"
          :id="'service-' + service.id"
          class="scroll-mt-32 border-gray-200"
          :class="[
            'border-t py-12 transition-colors',
            index === services.length - 1 ? 'border-b' : '',
            expandedService === service.id ? 'bg-white px-6 -mx-6' : 'group hover:bg-white px-6 -mx-6'
          ]"
        >
          <!-- Service Header -->
          <div 
            class="flex items-center justify-between cursor-pointer gap-4"
            @click="toggleService(service.id)"
          >
            <div class="flex items-center gap-4 md:gap-8">
              <span class="text-lg font-medium text-gray-400 shrink-0">({{ String(index + 1).padStart(2, '0') }})</span>
              <h3 class="text-xl md:text-3xl font-semibold text-gray-900">{{ service.title }}</h3>
            </div>
            <button 
              :class="[
                'w-10 h-10 md:w-12 md:h-12 rounded-full text-white flex items-center justify-center transition-colors shrink-0',
                expandedService === service.id ? 'bg-black hover:bg-gray-800' : 'bg-gray-700 hover:bg-black'
              ]"
            >
              <svg class="w-4 h-4 md:w-5 md:h-5 rotate-45" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3"></path>
              </svg>
            </button>
          </div>

          <!-- Expanded Content -->
          <transition name="expand">
            <div v-if="expandedService === service.id" class="mt-8">
              <div class="flex flex-col md:flex-row gap-8 items-center pl-0 md:pl-20">
                <!-- Image -->
                <div class="w-full md:w-auto shrink-0">
                  <img 
                    :src="service.image" 
                    :alt="service.title" 
                    class="rounded-2xl w-full md:w-[300px] h-[200px] object-cover shadow-lg"
                  >
                </div>

                <!-- Details -->
                <div class="grow flex items-center justify-between w-full">
                  <div class="space-y-3">
                    <div 
                      v-for="feature in service.features" 
                      :key="feature"
                      class="flex items-center gap-3 text-gray-700"
                    >
                      <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
                      </svg>
                      <span class="text-base">{{ feature }}</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </transition>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const expandedService = ref(null); // No service expanded by default

onMounted(() => {
  // Check if URL has a hash matching a service
  const hash = window.location.hash;
  if (hash && hash.startsWith('#service-')) {
    const serviceId = parseInt(hash.replace('#service-', ''));
    if (!isNaN(serviceId)) {
      // Small delay to ensure smooth scrolling calculation if needed, 
      // but purely setting state should be instant. 
      // Expanding immediately so user sees it open when they arrive.
      expandedService.value = serviceId;
    }
  }
});

const services = [
  {
    id: 1,
    title: 'UI/UX Design',
    image: 'https://images.unsplash.com/photo-1561070791-2526d30994b5?w=400&h=250&fit=crop',
    features: ['User Research', 'Wireframing', 'Prototyping']
  },
  {
    id: 2,
    title: 'Website Design',
    image: 'https://images.unsplash.com/photo-1498050108023-c5249f4df085?w=400&h=250&fit=crop',
    features: ['Responsive Design', 'Visual Mockups', 'Visual Designs']
  },
  {
    id: 3,
    title: 'Development',
    image: 'https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=400&h=250&fit=crop',
    features: ['Frontend Development']
  }
];

const toggleService = (serviceId) => {
  expandedService.value = expandedService.value === serviceId ? null : serviceId;
};
</script>

<style scoped>
.expand-enter-active,
.expand-leave-active {
  transition: all 0.3s ease;
  overflow: hidden;
}

.expand-enter-from,
.expand-leave-to {
  opacity: 0;
  max-height: 0;
}

.expand-enter-to,
.expand-leave-from {
  opacity: 1;
  max-height: 500px;
}
</style>
