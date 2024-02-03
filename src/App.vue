<script setup>
import Hero from "./components/Hero.vue";
import Navbar from "./components/Navbar.vue";
import Order from "./components/Order.vue";
import Footer from "./components/Footer.vue";
</script>

<template>
  <Navbar />
  <Hero />
  <Order />
  <div>
    <hr />
  </div>
  <Footer />
</template>

<style scoped>
div {
  width: 100%;
  max-width: 80%;
  margin: 0 auto;
}
</style>
