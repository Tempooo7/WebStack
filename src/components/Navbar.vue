<template>
  <nav class="w-full bg-white py-6">
    <div class="container mx-auto px-6 flex justify-between items-center text-black">
      <!-- Logo -->
      <div class="flex items-center gap-3">
        <img class="w-48" src="../assets/Image/Frame 35.svg" alt="WebStack Technology Logo">
      </div>
      
      <!-- Nav Links -->
      <div class="hidden md:flex items-center space-x-8 font-medium text-sm">
        <a href="#" class="border-b-2 border-black pb-1">Home</a>
        <a href="#about" class="text-gray-600 hover:text-black transition-colors">About</a>
        <a href="#services" class="text-gray-600 hover:text-black transition-colors">Services</a>
        <a href="#projects" class="text-gray-600 hover:text-black transition-colors">Work</a>
        <a href="#pricing" class="text-gray-600 hover:text-black transition-colors">Pricing</a>
        <a href="#faq" class="text-gray-600 hover:text-black transition-colors">Questions</a>
      </div>

      <!-- Button -->
      <button class="bg-black text-white px-8 py-3 rounded-full font-bold hover:bg-gray-800 transition-all duration-300 text-sm">
        Get Started
      </button>
    </div>
  </nav>
</template>

<script setup>
</script>
