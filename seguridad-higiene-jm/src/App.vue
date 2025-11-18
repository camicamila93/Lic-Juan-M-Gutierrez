<template>
  <v-app>
    <Banner />
    <About />
    <Works />
    <Services />
    <Contact />
  </v-app>
</template>

<script setup>
import Banner from './components/Banner.vue'
import About from './components/About.vue'
import Works from './components/Works.vue'
import Services from './components/Services.vue'
import Contact from './components/Contact.vue'
</script>

<style>
body {
  font-family: 'Open Sans', sans-serif;
  background-color: #f5f5f5;
  margin: 0;
}
</style>