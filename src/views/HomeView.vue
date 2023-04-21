<script setup>
import LandingSection from '../components/sections/LandingSection.vue';
import AboutSection from '../components/sections/AboutSection.vue';
import WorksSection from '../components/sections/WorksSection.vue';
import WhatWeDoSection from '../components/sections/WhatWeDoSection.vue';
import ContactSection from '../components/sections/ContactSection.vue';
</script>

<template>
  <main class="homepage">
    <LandingSection />
    <AboutSection />
    <WorksSection />
    <WhatWeDoSection />
    <ContactSection />
  </main>
</template>

<style lang="scss">
.homepage{
  position: relative;
  scroll-behavior: smooth;
  // scroll-snap-type: y proximity;
  // scroll-snap-stop: always;
  // scroll-padding-top: var(--nav-height);
  width: 100%;

  .section{
    border-bottom: 1px solid transparentize($color: vars.$secondary-color, $amount: 0.8);
    display: flex;
    min-height: 100vh;
    width: 100%;
    padding-top: var(--nav-height);
    padding-left: 6vw;
    padding-right: 6vw;
    overflow: hidden;
  }
}
</style>
