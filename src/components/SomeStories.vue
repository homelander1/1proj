<template>
    <section class="py-40">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <!-- Heading -->
            <div class="flex items-center">
                <div class="stories text-[60px]">Stories</div>
                <img src="../assets/images/Pasta.svg" alt="Stories icon" class="w-30 h-30 ml-4 m-2" />
            </div>

            <!-- Cards Grid -->
            <div class="grid grid-cols-1 md:grid-cols-3 gap-10 pt-6">
                <div v-for="story in stories" :key="story.id"
                    class="border-3 border-black rounded-xl overflow-hidden flex flex-col">
                    <!-- Image -->
                    <img :src="story.image" :alt="story.heading"
                        class="w-full h-49 object-cover border-b-3 border-black" />

                    <!-- Content -->
                    <div class="p-3 flex-1 flex flex-col text-center">
                        <div class="theading uppercase">
                            {{ story.heading }}
                        </div>
                        <p class="text-gray-700 flex-1 mt-3 mb-2">
                            {{ story.text }}
                        </p>
                        <a href="#"
                            class="mt-0 inline-block text-center bg-gray-100 py-2 rounded-lg hover:bg-green-900">
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
import img1 from '@/assets/images/story1.png'
import img2 from '@/assets/images/story2.png'
import img3 from '@/assets/images/story3.png'

const stories = ref([
    {
        id: 1,
        image: img1,
        heading: 'Chowdeck is Now in Ghana — Here’s What We Have in Store',
        text: `After months of planning, training, and listening, we’re excited to officially launch Chowdeck in Ghana!`,
    },
    {
        id: 2,
        image: img2,
        heading: '#AcceleratingYou: Celebrating Women-Led Brands in the Chowdeck Ecosystem',
        text: `The world flourishes when women lead. For International Women's Day, #AcceleratingYou celebrates truly brilliant women.`,
    },
    {
        id: 3,
        image: img3,
        heading: 'Get Free Deliveries and Reduced Service Fees with Chowpass!',
        text: `What if we told you there’s a way to save on delivery fees, service charges, and surge fees? It's called Chowpass!`,
    },
])
</script>

<style scoped>
.stories {
    font-weight: 700
}

.theading {
    font-weight: 700;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
    font-size: 13px;
    letter-spacing: -0.5px;
}

p {
    font-weight: 600;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    font-size: 20px;
    letter-spacing: -0.5px;
    line-height: 24px;
}

a {
    text-decoration: none;
    color: green;
    font-size: 17px;
}

a:hover {
    color: white;
}
</style>
