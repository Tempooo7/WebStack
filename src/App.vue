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

import { onMounted } from 'vue';

onMounted(() => {
  const observerOptions = {
    root: null,
    rootMargin: '0px',
    threshold: 0.1
  };

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('is-visible');
        observer.unobserve(entry.target); 
      }
    });
  }, observerOptions);

  const sections = document.querySelectorAll('.fade-in-section');
  sections.forEach(section => {
    observer.observe(section);
  });
});
</script>
