<script setup lang="ts">
import AbouSection from './components/section/AbouSection.vue'
import EducatioSection from './components/section/EducatioSection.vue'
import ExperienceSection from './components/section/ExperienceSection.vue'
//import ExperienceSection from './components/section/ExperienceSection.vue'
import HeroSection from './components/section/HeroSection.vue'
import ProjectSection from './components/section/ProjectSection.vue'
import SkillsSection from './components/section/SkillsSection.vue'
</script>

<template>
  <main>
    <HeroSection />
    <AbouSection />
    <!-- Cuando tenga experiencia laboral <ExperienceSection/> --->
    <ProjectSection />
    <EducatioSection />
    <SkillsSection />
  </main>
</template>

<style>
main {
  padding: 4rem;
  margin: auto;
  width: 100%;
}
section {
  max-width: 700px;
  margin: 0 auto 48px;
}

h2 {
  margin-bottom: 8px;
  font-weight: 700;
  line-height: 1.5;
  font-size: 1.5rem;
}

@media (width <= 700px) {
  section {
    margin-bottom: 38px;
  }
}

@media print {
  .not-print {
    display: none;
  }
}
.print {
  display: none;
}

@media print {
  .print {
    display: block;
  }
}
</style>
