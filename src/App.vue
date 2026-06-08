<template>
  <div class="app-shell">
    <a href="#main-content" class="skip-link">Pular para conteúdo</a>
    <Navbar />
    <main id="main-content">
      <Hero />
      <About />
      <Projects />
      <Contact />
    </main>
  </div>
</template>

<script setup>
import Navbar from "./components/Navbar.vue";
import Hero from "./components/Hero.vue";
import About from "./components/About.vue";
import Projects from "./components/Projects.vue";
import Contact from "./components/Contact.vue";
</script>

<style scoped>
.app-shell {
  position: relative;
}
</style>
