<script setup>
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import Services from './components/Services.vue'
import Cases from './components/Cases.vue'
import Contact from './components/Contact.vue'
import Footer from './components/Footer.vue'
import BackToTop from './components/BackToTop.vue'
import ConsultBtn from './components/ConsultBtn.vue'
</script>

<template>
  <Navbar />
  <main>
    <Hero />
    <Services />
    <Cases />
    <Contact />
  </main>
  <Footer />
  <BackToTop />
  <ConsultBtn />
</template>
