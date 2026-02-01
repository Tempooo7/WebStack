<template>
  <section id="pricing" class="py-6 px-4 text-white fade-in-section">
    <div class="container mx-auto relative bg-[#050203] text-white rounded-[40px] overflow-hidden min-h-[85vh] flex flex-col justify-between p-8 md:p-16">
      <!-- Header -->
      <div class="flex justify-between items-center mb-16">
        <h2 class="text-4xl md:text-6xl font-bold">Pricing Plan</h2>
        <div class="hidden md:flex items-center gap-2 text-sm font-medium">
          <span>Our Pricing</span>
          <div class="w-2 h-2 bg-white rounded-full"></div>
        </div>
      </div>

      <!-- Pricing Cards -->
      <div class="grid md:grid-cols-2 gap-8">
        <!-- Starter Plan -->
        <div class="bg-[#050203] border border-white rounded-3xl p-8 hover:border-gray-600 transition-colors">
          <!-- Header -->
          <div class="flex justify-between items-start mb-6">
            <div>
              <h3 class="text-lg font-medium text-gray-300 mb-3">Starter Plan</h3>
              <div class="text-4xl font-bold mb-2">
                499 LYD <span class="text-xl font-normal text-gray-400">/ Project</span>
              </div>
            </div>
            <svg class="w-6 h-6 text-gray-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11.049 2.927c.3-.921 1.603-.921 1.902 0l1.519 4.674a1 1 0 00.95.69h4.915c.969 0 1.371 1.24.588 1.81l-3.976 2.888a1 1 0 00-.363 1.118l1.518 4.674c.3.922-.755 1.688-1.538 1.118l-3.976-2.888a1 1 0 00-1.176 0l-3.976 2.888c-.783.57-1.838-.197-1.538-1.118l1.518-4.674a1 1 0 00-.363-1.118l-3.976-2.888c-.784-.57-.38-1.81.588-1.81h4.914a1 1 0 00.951-.69l1.519-4.674z"></path>
            </svg>
          </div>

          <p class="text-gray-400 text-sm mb-8 pb-8 border-b border-gray-700">
            Perfect for small businesses & personal brands
          </p>

          <!-- Features -->
          <div class="mb-8">
            <h4 class="font-semibold mb-4">What's Included:</h4>
            <ul class="space-y-3 text-sm text-gray-300">
              <li class="flex items-start gap-2">
                <span class="text-white">•</span>
                <span>1-3 page website</span>
              </li>
              <li class="flex items-start gap-2">
                <span class="text-white">•</span>
                <span>UI/UX design (Figma)</span>
              </li>
              <li class="flex items-start gap-2">
                <span class="text-white">•</span>
                <span>Responsive design</span>
              </li>
              <li class="flex items-start gap-2">
                <span class="text-white">•</span>
                <span>Basic SEO setup</span>
              </li>
              <li class="flex items-start gap-2">
                <span class="text-white">•</span>
                <span>1 revision round</span>
              </li>
              <li class="flex items-start gap-2">
                <span class="text-white">•</span>
                <span>Delivery in 7 days</span>
              </li>
            </ul>
          </div>

          <!-- Button -->
          <a href="#contact" class="block w-full text-center bg-white text-black py-4 rounded-full font-bold hover:bg-gray-100 transition-colors">
            Get Started
          </a>
        </div>

        <!-- Professional Plan -->
        <div class="bg-white text-gray-900 rounded-3xl p-8 hover:shadow-2xl transition-shadow">
          <!-- Header -->
          <div class="flex justify-between items-start mb-6">
            <div>
              <h3 class="text-lg font-medium text-gray-700 mb-3">
                Professional Plan <span class="text-sm">(Most Popular)</span>
              </h3>
              <div class="text-4xl font-bold mb-2">
                1,299 LYD <span class="text-xl font-normal text-gray-600">/ Project</span>
              </div>
            </div>
            <svg class="w-6 h-6 text-gray-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11.049 2.927c.3-.921 1.603-.921 1.902 0l1.519 4.674a1 1 0 00.95.69h4.915c.969 0 1.371 1.24.588 1.81l-3.976 2.888a1 1 0 00-.363 1.118l1.518 4.674c.3.922-.755 1.688-1.538 1.118l-3.976-2.888a1 1 0 00-1.176 0l-3.976 2.888c-.783.57-1.838-.197-1.538-1.118l1.518-4.674a1 1 0 00-.363-1.118l-3.976-2.888c-.784-.57-.38-1.81.588-1.81h4.914a1 1 0 00.951-.69l1.519-4.674z"></path>
            </svg>
          </div>

          <p class="text-gray-600 text-sm mb-8 pb-8 border-b border-gray-200">
            Ideal for growing startups
          </p>

          <!-- Features -->
          <div class="mb-8">
            <h4 class="font-semibold mb-4">What's Included:</h4>
            <ul class="space-y-3 text-sm text-gray-700">
              <li class="flex items-start gap-2">
                <span class="text-black">•</span>
                <span>Up to 8 pages</span>
              </li>
              <li class="flex items-start gap-2">
                <span class="text-black">•</span>
                <span>Full UI/UX design system</span>
              </li>
              <li class="flex items-start gap-2">
                <span class="text-black">•</span>
                <span>Frontend development</span>
              </li>
              <li class="flex items-start gap-2">
                <span class="text-black">•</span>
                <span>SEO-ready structure</span>
              </li>
              <li class="flex items-start gap-2">
                <span class="text-black">•</span>
                <span>3 revision rounds</span>
              </li>
              <li class="flex items-start gap-2">
                <span class="text-black">•</span>
                <span>Delivery in 14 days</span>
              </li>
            </ul>
          </div>

          <!-- Button -->
          <a href="#contact" class="block w-full text-center bg-black text-white py-4 rounded-full font-bold hover:bg-gray-800 transition-colors">
            Get Started
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>
