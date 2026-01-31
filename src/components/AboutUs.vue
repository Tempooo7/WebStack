<template>
  <section class="bg-white py-6 px-4">
    <div class="container mx-auto relative bg-black text-white rounded-[40px] overflow-hidden min-h-[85vh] flex flex-col justify-between p-8 md:p-16">
      <!-- About Us Header -->
      <div class="flex items-center gap-3 mb-8">
        <div class="w-3 h-3 bg-white rounded-full"></div>
        <h2 class="text-base font-semibold">About Us</h2>
      </div>

     <!-- Description -->
<div class="max-w-3xl mb-16 ml-auto">
  <p class="text-[16px] md:text-[24px] leading-relaxed">
    We're a creative team helping brands grow through strategy, 
    <span class="font-bold">UI/UX design</span>, and <span class="font-bold">Development</span>. 
    Our focus is on building meaningful digital experiences that are simple, functional, and impactful.
  </p>
</div>


      <!-- Stats Cards -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <!-- Project Prototype Card -->
        <div class="bg-white text-black p-8 rounded-3xl flex flex-col justify-between min-h-[200px]">
          <div class="text-sm font-medium text-gray-600 mb-auto">Project Prototype</div>
          <div class="text-6xl font-bold">800+</div>
        </div>

        <!-- Project Delivery Card -->
        <div class="bg-white text-black p-8 rounded-3xl flex flex-col justify-between min-h-[200px]">
          <div class="text-sm font-medium text-gray-600 mb-auto">Project Delivery</div>
          <div class="text-6xl font-bold">500+</div>
        </div>

        <!-- Satisfied Clients Card (Gray) -->
        <div class="bg-gray-600 text-white p-8 rounded-3xl flex flex-col justify-between min-h-[200px]">
          <div class="text-6xl font-bold mb-auto">10K</div>
          <div class="text-sm font-medium text-gray-200">Satisfied Clients</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>
