<template>
    <section class="py-12 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <!-- Section Heading -->
            <h2 class="text-4xl font-bold text-center text-gray-300 mb-12 flex justify-center items-center">
                <span>Join our growing network</span>
                <svg class="w-6 h-6 ml-2 text-gray-300 animate-bounce" fill="none" stroke="currentColor"
                    viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
                </svg>
            </h2>

            <!-- Cards Grid -->
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div v-for="item in cards" :key="item.title"
                    class="flex flex-col border-2 border-black rounded-2xl overflow-hidden">
                    <!-- Card Body -->
                    <div class="p-6 flex-1 flex flex-col">
                        <!-- Icon -->
                        <div class="text-3xl mb-4">
                            {{ item.icon }}
                        </div>
                        <!-- Title -->
                        <h3 class="text-xl font-bold">
                            {{ item.title }}
                        </h3>
                        <!-- Description -->
                        <p class="text-gray-700 mt-2 flex-1">
                            {{ item.description }}
                        </p>
                        <!-- See More Link -->
                        <a :href="item.link"
                            class="mt-4 inline-flex items-center text-sm font-semibold uppercase hover:text-yellow-500">
                            See More
                            <svg class="w-4 h-4 ml-1" fill="currentColor" viewBox="0 0 20 20">
                                <path
                                    d="M12.293 5.293a1 1 0 011.414 1.414L10.414 10l3.293 3.293a1 1 0 01-1.414 1.414l-4-4a1 1 0 010-1.414l4-4z" />
                            </svg>
                        </a>
                    </div>
                    <!-- Card Image -->
                    <div class="h-40 overflow-hidden">
                        <img :src="item.image" :alt="item.title" class="w-full h-full object-cover" />
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue'

// import each asset so the bundler knows to include it
import img1 from '@/assets/images/card1.png'
import img2 from '@/assets/images/card2.png'
import img3 from '@/assets/images/card3.png'

const cards = ref([
    {
        icon: '🌟',
        title: 'Start selling',
        description: 'Are you a restaurant owner…',
        link: '/vendors',
        image: img1,        // ← now a proper URL
    },
    {
        icon: '🛵',
        title: 'Deliver happiness',
        description: 'Join our elite league…',
        link: '/riders',
        image: img2,
    },
    {
        icon: '✨',
        title: 'Behind the scenes',
        description: 'If you are passionate…',
        link: '/careers',
        image: img3,
    },
])
</script>


<style scoped></style>
