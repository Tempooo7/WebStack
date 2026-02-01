<template>
  <section id="testimonials" class="py-6 px-4 fade-in-section">
    <div class="container mx-auto relative bg-[#F7F7F7] text-white rounded-[40px] overflow-hidden min-h-[85vh] flex flex-col justify-between p-8 md:p-16">
      <!-- Header -->
      <div class="flex justify-between items-start mb-16">
        <h2 class="text-6xl font-bold text-gray-900 max-w-md leading-tight">
          What Clients<br>Are Saying
        </h2>
        <div class="hidden md:flex items-center gap-2 text-sm font-medium">
           <div class="w-3 h-3 bg-black rounded-full"></div>
        <h2 class="text-base font-semibold text-black">Services</h2>
      </div>
      </div>

      <!-- Testimonials Grid -->
      <div class="grid md:grid-cols-2 gap-6">
        <!-- Left Column: Text Testimonials -->
        <div class="space-y-6">
          <div 
            v-for="testimonial in testimonials.slice(0, 3)" 
            :key="testimonial.id"
            class="bg-white border border-gray-200 rounded-3xl p-6 hover:shadow-lg transition-shadow"
          >
            <!-- Stars -->
            <div class="flex gap-1 mb-4">
              <svg 
                v-for="star in 5" 
                :key="star"
                :class="star <= testimonial.rating ? 'text-orange-500' : 'text-gray-300'"
                class="w-5 h-5 fill-current"
                viewBox="0 0 20 20"
              >
                <path d="M10 15l-5.878 3.09 1.123-6.545L.489 6.91l6.572-.955L10 0l2.939 5.955 6.572.955-4.756 4.635 1.123 6.545z"/>
              </svg>
            </div>

            <!-- Quote -->
            <p class="text-gray-900 text-lg mb-6 leading-relaxed">
              "{{ testimonial.quote }}"
            </p>

            <!-- Author -->
            <div class="flex items-center gap-3">
              <img 
                :src="testimonial.avatar" 
                :alt="testimonial.name"
                class="w-12 h-12 rounded-full object-cover"
              >
              <div>
                <div class="font-semibold text-gray-900">{{ testimonial.role }}</div>
                <div class="text-sm text-gray-600">{{ testimonial.name }}</div>
              </div>
            </div>
          </div>
        </div>

        <!-- Right Column: Video + Additional Testimonial -->
        <div class="space-y-6">
          <!-- Top Testimonial -->
          <div class="bg-white border border-gray-200 rounded-3xl p-6 hover:shadow-lg transition-shadow">
            <!-- Stars -->
            <div class="flex gap-1 mb-4">
              <svg 
                v-for="star in 5" 
                :key="star"
                :class="star <= 4 ? 'text-orange-500' : 'text-gray-300'"
                class="w-5 h-5 fill-current"
                viewBox="0 0 20 20"
              >
                <path d="M10 15l-5.878 3.09 1.123-6.545L.489 6.91l6.572-.955L10 0l2.939 5.955 6.572.955-4.756 4.635 1.123 6.545z"/>
              </svg>
            </div>

            <!-- Quote -->
            <p class="text-gray-900 text-base mb-6 leading-relaxed">
              "The UI/UX work was thoughtful and well-structured. Every design decision made sense, and the final result was both modern and easy to use."
            </p>

            <!-- Author -->
            <div class="flex items-center gap-3">
              <img 
                src="https://i.pravatar.cc/150?img=33"
                alt="Product Manager"
                class="w-12 h-12 rounded-full object-cover"
              >
              <div>
                <div class="font-semibold text-gray-900">Product Manager</div>
                <div class="text-sm text-gray-600">Ahmed K</div>
              </div>
            </div>
          </div>

          <!-- Video Testimonial -->
          <div class="relative bg-gray-700 rounded-3xl overflow-hidden h-[380px] group cursor-pointer">
            <video 
                src="../assets/Image/Gen-4 Turbo make it so he is talking and like giving a testimonail  3472740700.mp4" 
                playsinline
                autoplay
                loop              
                muted 
                class="absolute inset-0 w-full h-full object-cover"
            ></video>
            
         
            <!-- Author Info -->
            <div class="absolute bottom-6 left-6 text-white">
              <div class="font-semibold">Master of Lead</div>
              <div class="text-sm opacity-90">Daniel T</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';

const testimonials = ref([
  {
    id: 1,
    rating: 4,
    quote: "Working with this team was smooth from start to finish. They really understood our vision and turned it into a clean, user-friendly website that performs beautifully.",
    role: "Startup Founder",
    name: "Sarah M",
    avatar: "https://i.pravatar.cc/150?img=5"
  },
  {
    id: 2,
    rating: 4,
    quote: "They didn't just design a website, they created an experience. Communication was clear, timelines were respected, and the outcome exceeded expectations.",
    role: "Marketing Lead",
    name: "Daniel T",
    avatar: "https://i.pravatar.cc/150?img=12"
  },
  {
    id: 3,
    rating: 4,
    quote: "The UI/UX work was thoughtful and well-structured. Every design decision made sense, and the final result was both modern and easy to use.",
    role: "Product Manager",
    name: "Ahmed K",
    avatar: "https://i.pravatar.cc/150?img=33"
  }
]);
</script>

<style scoped>
</style>
