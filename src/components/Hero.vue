<template>
  <section id="home" class="bg-white py-6 px-4 fade-in-section">
    <div class="container mx-auto relative bg-black text-white rounded-[40px] overflow-hidden min-h-[85vh] flex flex-col justify-between p-8 md:p-16">
        
        <!-- Vibrant Wave Background -->
        <div class="absolute inset-0 z-0 overflow-hidden pointer-events-none">
            <video 
                src="../assets/Image/Gen-4 Turbo a weavy transation in video 2133558651.mp4" 
                autoplay 
                loop 
                muted 
                class="absolute inset-0 w-full h-full object-cover"
            ></video>
        </div>

        <!-- Content Grid -->
        <div class="relative z-10 grid md:grid-cols-2 gap-12 items-start mt-8 mb-auto">
            <!-- Left: Heading -->
            <div class="max-w-xl">
                <h1 class="md:text-[24px] font-normal leading-[1.1] tracking-tight">
                    We <span class="font-bold">Design</span> and <span class="font-bold">Build</span> digital experiences<br>
                    that actually work
                </h1>
            </div>

            <!-- Right: Button and List -->
            <div class="flex flex-col items-end space-y-6 pt-4">
                <!-- White Button -->
               <a href="#contact" class="w-[320px] bg-white text-black px-10 py-4 rounded-full font-bold hover:bg-gray-100 transition-colors text-base text-center inline-block">
  Get Started
</a>


                <!-- White Card List -->
                <div class="bg-white/95 backdrop-blur-sm text-black rounded-3xl overflow-hidden w-full md:max-w-[320px] shadow-xl">
                    <div class="flex flex-col">
                        <a href="#service-2" class="flex items-center justify-between px-6 py-5 border-b border-gray-200 hover:bg-gray-50 transition-colors cursor-pointer group">
                             <span class="font-semibold text-base">Websites Designs</span>
                             <svg class="w-5 h-5 opacity-60 group-hover:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"></path></svg>
                        </a>
                        <a href="#service-1" class="flex items-center justify-between px-6 py-5 border-b border-gray-200 hover:bg-gray-50 transition-colors cursor-pointer group">
                             <span class="font-semibold text-base">UI/UX Designs</span>
                             <svg class="w-5 h-5 opacity-60 group-hover:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"></path></svg>
                        </a>
                        <a href="#service-3" class="flex items-center justify-between px-6 py-5 hover:bg-gray-50 transition-colors cursor-pointer group">
                             <span class="font-semibold text-base">Development</span>
                             <svg class="w-5 h-5 opacity-60 group-hover:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"></path></svg>
                        </a>
                    </div>
                </div>
            </div>
        </div>

        <!-- Bottom Footer -->
        <div class="relative z-10 mt-16">
            <div class="flex flex-col justify-center items-start">
                 <div class="text-sm text-gray-300 w-full md:w-[400px] pl-0 md:pl-[58px] mb-8 md:mb-12 mt-0 md:mt-0 md:-ml-16">
                    <span class="font-bold text-white ">WebStack</span> Helps You Turn Your Work into Something People Remember.
                </div>
                <h2 class="text-[48px] md:text-[100px] lg:text-[100px] font-bold leading-[0.85] tracking-tighter text-white -ml-2 mb-[-10px]">
                    WebStack
                </h2>      
                
            </div>
        </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
</style>
 