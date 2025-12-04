<script setup>
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import AnalyticsDashboard from './components/AnalyticsDashboard.vue'
import ServicesGrid from './components/ServicesGrid.vue'
import ProcessTimeline from './components/ProcessTimeline.vue'
import PricingSection from './components/PricingSection.vue'
import AdvantagesSection from './components/AdvantagesSection.vue'
import CasesSection from './components/CasesSection.vue'
import FAQSection from './components/FAQSection.vue'
import ContactSection from './components/ContactSection.vue'
import FooterSection from './components/FooterSection.vue'
import { onMounted } from 'vue'

onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible')
        
        // Animate charts if present
        if (entry.target.classList.contains('case-card')) {
          const bar = entry.target.querySelector('.chart-bar')
          if (bar) {
            bar.style.height = bar.dataset.height
          }
        }
      }
    })
  }, { threshold: 0.1 })

  document.querySelectorAll('.animate-in, .case-card').forEach(el => {
    observer.observe(el)
  })
})
</script>

<template>
  <div class="app-wrapper">
    <NavBar />
    <main>
      <HeroSection />
      <AnalyticsDashboard />
      <AdvantagesSection />
      <ServicesGrid />
      <ProcessTimeline />
      <CasesSection />
      <PricingSection />
      <FAQSection />
      <ContactSection />
    </main>
    <FooterSection />
  </div>
</template>

<style>
.app-wrapper {
  width: 100%;
  overflow-x: hidden;
  background-color: var(--color-bg-primary);
  color: var(--color-text-primary);
}

/* Global Animation Classes */
.animate-in {
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.6s ease-out, transform 0.6s ease-out;
}

.animate-in.visible {
  opacity: 1;
  transform: translateY(0);
}
</style>
