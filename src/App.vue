<template>
  <div class="antialiased text-slate-800 bg-white selection:bg-primary selection:text-white">
    <Navbar />
    <main>
      <Hero />
      <AboutUs />
      <Services />
      <Projects />
      <Testimonials />
      <Team />
      <Pricing />
      <FAQ />
    </main>
    <Footer />
  </div>
</template>

<script setup>
import Navbar from './components/Navbar.vue';
import Hero from './components/Hero.vue';
import AboutUs from './components/AboutUs.vue';
import Services from './components/Services.vue';
import Projects from './components/Projects.vue';
import Testimonials from './components/Testimonials.vue';
import Team from './components/Team.vue';
import Pricing from './components/Pricing.vue';
import FAQ from './components/FAQ.vue';
import Footer from './components/Footer.vue';
</script>
