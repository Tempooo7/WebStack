<template>
  <section id="faq" class="py-10 md:py-20 bg-gray-50 fade-in-section">
    <div class="container mx-auto px-6">
      <!-- Header -->
      <div class="flex flex-col md:flex-row justify-between items-start md:items-center mb-8 md:mb-16 gap-4 md:gap-0">
        <h2 class="text-4xl md:text-6xl font-bold text-gray-900">Questions</h2>
        <div class="flex items-center gap-2 text-sm font-medium">
          <span>FAQ</span>
          <div class="w-2 h-2 bg-black rounded-full"></div>
        </div>
      </div>

      <!-- FAQ List -->
      <div class="max-w-4xl mx-auto space-y-0">
        <div 
          v-for="(faq, index) in faqs" 
          :key="faq.id"
          :class="[
            'border-t border-gray-200 py-8 transition-colors',
            index === faqs.length - 1 ? 'border-b' : ''
          ]"
        >
          <!-- Question Header -->
          <div 
            class="flex items-start justify-between cursor-pointer gap-8"
            @click="toggleFaq(faq.id)"
          >
            <div class="flex items-start gap-6 grow">
              <span class="text-lg font-medium text-gray-400 shrink-0">
                ({{ String(index + 1).padStart(2, '0') }})
              </span>
              <h3 class="text-2xl font-semibold text-gray-900 leading-tight">
                {{ faq.question }}
              </h3>
            </div>
            
            <!-- Toggle Icon -->
            <button 
              class="text-3xl text-gray-900 w-8 h-8 flex items-center justify-center shrink-0 transition-transform"
              :class="{ 'rotate-45': expandedFaq === faq.id }"
            >
              {{ expandedFaq === faq.id ? '−' : '+' }}
            </button>
          </div>

          <!-- Answer -->
          <transition name="expand">
            <div v-if="expandedFaq === faq.id" class="mt-6 ml-[72px]">
              <p class="text-gray-700 leading-relaxed">
                {{ faq.answer }}
              </p>
            </div>
          </transition>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';

const expandedFaq = ref(1); // Default to first question expanded

const faqs = [
  {
    id: 1,
    question: 'How long does it take to design and develop a website?',
    answer: 'Most projects take between 1-3 weeks, depending on the size and complexity. We always share a clear timeline before starting.'
  },
  {
    id: 2,
    question: 'Do you offer UI/UX design only?',
    answer: 'Yes, we offer standalone UI/UX design services. You can choose to have just the design phase, or bundle it with development for a complete solution.'
  },
  {
    id: 3,
    question: 'Will my website be mobile-friendly?',
    answer: 'Absolutely! All our designs are fully responsive and optimized for mobile, tablet, and desktop devices to ensure a seamless experience across all screen sizes.'
  },
  {
    id: 4,
    question: 'Can I request changes during the project?',
    answer: 'Yes, we include revision rounds in all our packages. The number of revisions depends on your chosen plan, and we\'re always open to feedback throughout the process.'
  }
];

const toggleFaq = (faqId) => {
  expandedFaq.value = expandedFaq.value === faqId ? null : faqId;
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
  max-height: 200px;
}
</style>
