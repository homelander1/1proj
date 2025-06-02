<template>
  <!-- ...your visible code... -->
  <!-- Hidden preloads -->
  <div style="display:none;">
    <img src="../assets/images/phone2.png" alt="">
    <img src="../assets/images/phone3.png" alt="">
    <img src="../assets/images/phone4.png" alt="">
  </div>
  <div class="max-w-[352px] mx-auto my-5">
    <!-- Toggle Switch -->
    <div class="flex justify-center mb-8 ">
      <div class="relative inline-flex bg-yellow-50 rounded-full overflow-hidden w-full">
        <!-- Sliding Highlight -->
        <span class="absolute top-0 bottom-0 bg-yellow-400 rounded-full transition-all duration-300 ease-in-out" :style="{
          width: `${100 / tabs.length}%`,
          transform: `translateX(${tabs.indexOf(activeTab) * 100}%)`
        }"></span>

        <!-- Tab Buttons -->
        <button v-for="tab in tabs" :key="tab" @click="activeTab = tab"
          class="relative z-10 flex-1 py-2 text-sm font-medium transition-colors duration-200" :class="activeTab === tab
            ? 'text-gray-800'
            : 'text-gray-800 hover:text-gray-900'">
          {{ tab }}
        </button>
      </div>
    </div>
  </div>
  <!-- Customer View -->
  <div v-if="activeTab === 'Customer'" class="text-center">
    <h2>Try the App</h2>
    <p class="text-gray-800 mb-6 max-w-[532px] mx-auto">
      Have meals delivered to you within minutes from a wide <br> variety of
      restaurants ranging from African to Continental <br> cuisines to satisfy
      your cravings.
    </p>
    <div class="flex justify-center space-x-4 mx-auto gap-2">
      <a href="#" class="w-12 h-12 bg-green-900 rounded-full flex items-center justify-center">
        <img src="../assets/images/play store android.png" alt="Google Play" class="w-5 h-5" />
      </a>
      <a href="#" class="w-12 h-12 bg-green-900 rounded-full flex items-center justify-center">
        <img src="../assets/images/apple store.png" alt="App Store" class="w-5 h-5" />
      </a>
    </div>
    <div class="relative phone-image">
      <img src="../assets/images/phone2.png" alt="App Screenshot" class="mx-auto w-80" />
      <div class="absolute -top-10 left-[53%]  flex items-center justify-center">
        <img src="../assets/images/plate.png" alt="" class="w-30 h-30" />
      </div>
    </div>
  </div>

  <!-- Vendors View -->
  <div v-else-if="activeTab === 'Vendors'" class="text-center">
    <h2>All in One</h2>
    <p>
      Unlock new levels of growth with seamless menu and orders <br> management, multiple branches and team, easy
      payouts <br> withdrawal and a lot more.


    </p>
    <div class="flex justify-center space-x-4 mx-auto gap-2">
      <a href="#" class="w-12 h-12 bg-green-900 rounded-full flex items-center justify-center">
        <img src="../assets/images/play store android.png" alt="Google Play" class="w-5 h-5" />
      </a>
      <a href="#" class="w-12 h-12 bg-green-900 rounded-full flex items-center justify-center">
        <img src="../assets/images/apple store.png" alt="App Store" class="w-5 h-5" />
      </a>
    </div>
    <div class="relative phone-image">
      <img src="../assets/images/phone3.png" alt="App Screenshot" class="mx-auto w-80" />
      <div class="absolute -top-10 left-[53%]  flex items-center justify-center">
        <img src="../assets/images/plate.png" alt="" class="w-30 h-30" />
      </div>
    </div>
  </div>


  <!-- Riders View -->
  <div v-else class="text-center">
    <h2>Become a Champ</h2>
    <p>
      Choose your own working hours, ride your choice of bike, <br> track your metrics, earn bonuses and withdraw easily
      to <br>
      your account. Do more with our app.
    </p>
    <div class="flex justify-center space-x-4 mx-auto gap-2">
      <a href="#" class="w-12 h-12 bg-green-900 rounded-full flex items-center justify-center">
        <img src="../assets/images/play store android.png" alt="Google Play" class="w-5 h-5" />
      </a>
      <a href="#" class="w-12 h-12 bg-green-900 rounded-full flex items-center justify-center">
        <img src="../assets/images/apple store.png" alt="App Store" class="w-5 h-5" />
      </a>
    </div>
    <div class="relative phone-image">
      <img src="../assets/images/phone4.png" alt="App Screenshot" class="mx-auto w-80" />
      <div class="absolute -top-10 left-[53%]  flex items-center justify-center">
        <img src="../assets/images/plate.png" alt="" class="w-30 h-30" />
      </div>
    </div>
  </div>


</template>

<script setup>
import { ref } from 'vue'

const tabs = ['Customer', 'Vendors', 'Riders']
const activeTab = ref('Customer')
</script>

<style scoped>
h2 {
  /* font-family: Roboto, sans-serif; */
  font-weight: 700;
  font-size: 42px;
  margin-top: 180px;
  margin-bottom: 20px;
  letter-spacing: -2px;
  margin: 12px 0;

}

.phone-image {
  margin-top: 60px;

}

p {
  font-size: 18px;

}
</style>
