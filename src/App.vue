<script setup>
// import { RouterLink, RouterView } from 'vue-router'


import HeroSection from './components/HeroSection.vue'
import CoolStuff from './components/CoolStuff.vue'
import PageFooter from './components/PageFooter.vue'
import helloAll from './components/helloAll.vue'
import JoinNet from './components/JoinNet.vue'
import CarouselSection from './components/CarouselSection.vue'
import FeaturesList from './components/FeaturesList.vue'
import RestaurantsMap from './components/RestaurantsMap.vue'
import SomeStories from './components/SomeStories.vue'
import FAQSection from './components/FAQSection.vue'
</script>

<template>
  <header>

    <div class="wrapper">


      <HeroSection />
      <helloAll />

      <JoinNet />
      <CarouselSection />
      <FeaturesList />
      <RestaurantsMap />
      <SomeStories />
      <FAQSection />


      <CoolStuff />
      <PageFooter />


      <!-- <nav> -->
      <!-- <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink> -->
      <!-- </nav> -->
    </div>
  </header>

  <!-- <RouterView /> -->
</template>

<style scoped></style>
