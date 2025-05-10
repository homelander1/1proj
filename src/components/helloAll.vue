<template>
  <div class="max-w-md mx-auto p-6">
    <!-- Toggle Switch -->
    <div class="flex justify-center mb-8">
      <div class="inline-flex bg-gray-200 rounded-full p-1">
        <button v-for="tab in tabs" :key="tab" @click="activeTab = tab" :class="[
          'px-4 py-2 rounded-full transition-colors duration-200',
          activeTab === tab
            ? 'bg-yellow-400 text-white'
            : 'text-gray-700 hover:bg-yellow-300'
        ]">
          {{ tab }}
        </button>
      </div>
    </div>

    <!-- Customer View -->
    <div v-if="activeTab === 'Customer'" class="text-center">
      <h2 class="text-4xl font-bold mb-4">Try the App</h2>
      <p class="text-gray-600 mb-6">
        Have meals delivered to you within minutes from a wide variety of
        restaurants ranging from African to Continental cuisines to satisfy
        your cravings.
      </p>
      <div class="flex justify-center space-x-4 mb-8">
        <a href="#" class="w-12 h-12 bg-green-800 rounded-full flex items-center justify-center">
          <img src="../assets/images/play store android.png" alt="Google Play" class="w-6 h-6" />
        </a>
        <a href="#" class="w-12 h-12 bg-green-800 rounded-full flex items-center justify-center">
          <img src="../assets/images/apple store.png" alt="App Store" class="w-6 h-6" />
        </a>
      </div>
      <div class="relative">
        <img src="../assets/images/phone2.png" alt="App Screenshot" class="mx-auto w-80" />
        <div class="absolute top-0 right-0 transform translate-x-1/4 -translate-y-1/4
                     w-42 h-12 flex items-center justify-center">
          <img src="../assets/images/plate.png" alt="" class="w-8 h-8" />
        </div>
      </div>
    </div>

    <!-- Vendors View -->
    <div v-else-if="activeTab === 'Vendors'" class="text-center">
      <h2 class="text-3xl font-semibold mb-4">Vendors Dashboard</h2>
      <p class="text-gray-600">
        Manage your restaurant, track orders in real-time, and view performance
        analytics—all from one place.
      </p>
      <!-- add more vendor-specific content here -->
    </div>

    <!-- Riders View -->
    <div v-else class="text-center">
      <h2 class="text-3xl font-semibold mb-4">Riders Panel</h2>
      <p class="text-gray-600">
        See your delivery assignments, update statuses, and track your earnings
        effortlessly.
      </p>
      <!-- add more rider-specific content here -->
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const tabs = ['Customer', 'Vendors', 'Riders']
const activeTab = ref('Customer')
</script>
