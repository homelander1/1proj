<template>
    <section class="py-12">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <!-- Heading -->
            <div class="flex items-center mb-8">
                <h2 class="text-4xl font-bold">Stories</h2>
                <img src="" alt="Stories icon" class="w-10 h-10 ml-4" />
            </div>

            <!-- Cards Grid -->
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div v-for="story in stories" :key="story.id"
                    class="border-2 border-black rounded-lg overflow-hidden flex flex-col">
                    <!-- Image -->
                    <img :src="story.image" :alt="story.heading" class="w-full h-40 object-cover" />

                    <!-- Content -->
                    <div class="p-4 flex-1 flex flex-col">
                        <h3 class="text-lg font-semibold mb-2">
                            {{ story.heading }}
                        </h3>
                        <p class="text-gray-700 flex-1 mb-4">
                            {{ story.text }}
                        </p>
                        <a href="#"
                            class="mt-auto inline-block text-center bg-green-100 text-green-800 py-2 rounded hover:bg-green-200 transition">
                            Read More
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue'

// replace these with your real image imports
import img1 from '@/assets/images/card1.png'
import img2 from '@/assets/images/card2.png'
import img3 from '@/assets/images/card3.png'

const stories = ref([
    {
        id: 1,
        image: img1,
        heading: '#ACCELERATINGYOU: Celebrating Women-led brands in the Chowdeck Ecosystem',
        text: `The world flourishes when women lead. For International Women's Day, 
#AcceleratingYou celebrates truly brilliant women.`,
    },
    {
        id: 2,
        image: img2,
        heading: 'Get Free Deliveries and Reduced Service Fees with Chowpass!',
        text: `What if we told you there’s a way to save on delivery fees, service charges, 
and surge fees? It’s called Chowpass!`,
    },
    {
        id: 3,
        image: img3,
        heading: 'Introducing Chowsmart: Zero Fees and Great Deals!',
        text: `With zero extra fees, affordable meals, and shorter wait times, 
Chowsmart will have you eating good!`,
    },
])
</script>

<style>
/* all styling via Tailwind */
</style>
