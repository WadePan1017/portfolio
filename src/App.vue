<script setup>
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import Timeline from './components/Timeline.vue'
import About from './components/About.vue'
import JobIntent from './components/JobIntent.vue'
import Skills from './components/Skills.vue'
import Projects from './components/Projects.vue'
import Services from './components/Services.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <Navbar />
  <main>
    <Hero />
    <Timeline />
    <About />
    <JobIntent />
    <Skills />
    <Projects />
    <Services />
    <Contact />
  </main>
  <Footer />
</template>
