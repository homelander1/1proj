<script setup>
// import { RouterLink, RouterView } from 'vue-router'

import PageHeader from './components/PageHeader.vue'

import CoolStuff from './components/CoolStuff.vue'
import PageFooter from './components/PageFooter.vue'
</script>

<template>
  <header>
    <!-- <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" /> -->

    <div class="wrapper">

      <PageHeader />



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
