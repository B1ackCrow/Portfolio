<template>
  <div class="portfolio">
    <HeroSection />
    <ProjectsSection />

    <div class="info-sections">
      <WhatIDoSection />
      <TechStackSection />
    </div>

    <ContactSection />
  </div>
</template>

<script setup>
import HeroSection from './components/HeroSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import WhatIDoSection from './components/WhatIDoSection.vue'
import TechStackSection from './components/TechStackSection.vue'
import ContactSection from './components/ContactSection.vue'
</script>

<style scoped>
.info-sections {
  display: grid;
  grid-template-columns: 1.8fr 1fr;

  background: var(--color-background);
}

.info-sections > :first-child {
  border-right: 1px solid var(--color-border);
}

@media (max-width: 900px) {
  .info-sections {
    grid-template-columns: 1fr;
  }

  .info-sections > :first-child {
    border-right: none;
    border-bottom: 1px solid var(--color-border);
  }
}
</style>