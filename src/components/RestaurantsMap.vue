<template>
    <div class="max-w-5xl mx-auto bg-white border border-black rounded-lg overflow-hidden flex h-[600px]">
        <!-- Left: static map image -->
        <div class="w-2/3">
            <img src="" alt="Map" class="w-full h-full object-cover" />
        </div>

        <!-- Right: scrollable list -->
        <div class="w-1/3 flex flex-col">
            <!-- Header -->
            <div class="bg-blue-300 px-4 py-3 border-b border-gray-200">
                <h3 class="text-lg font-semibold text-black">Restaurants</h3>
            </div>
            <!-- Scrollable list -->
            <div class="flex-1 overflow-y-auto bg-white">
                <ul class="p-2">
                    <li v-for="item in items" :key="item.name" class="mb-2">
                        <a :href="item.link"
                            class="flex justify-between items-center bg-white rounded-lg border border-gray-200 px-4 py-3 hover:bg-gray-100 transition-colors">
                            <span class="text-gray-800">{{ item.name }}</span>
                            <svg class="w-5 h-5 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M3 3h18v18H3V3z" />
                            </svg>
                        </a>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

const items = ref([
    { name: 'Item 7 (Go) – Bodija', link: '#' },
    { name: 'Iya Meta', link: '#' },
    { name: 'Amoke Oge – Oguntolu', link: '#' },
    { name: 'Mega Chicken – Ikeja', link: '#' },
    { name: 'IYA MORIA', link: '#' },
    { name: 'Red Pepper By FoodCourt', link: '#' },
    { name: 'Cravings N More – Egbeda', link: '#' },
    { name: 'King Glab Cuisine – Yaba', link: '#' },
    { name: 'Spice Garden – Lekki', link: '#' },
    { name: 'Ocean’s Catch – Surulere', link: '#' },
    { name: 'Urban Bites – Ogudu', link: '#' },
    { name: 'Mama’s Kitchen – Festac', link: '#' },
    { name: 'Green Bowl – Egbeda', link: '#' },
    { name: 'Sweet Treats – Gbagada', link: '#' },
    { name: 'Taste of Africa – Surulere', link: '#' },
])
</script>

<style>
/* custom scrollbar for WebKit browsers */
::-webkit-scrollbar {
    width: 8px;
}

::-webkit-scrollbar-track {
    background: transparent;
}

::-webkit-scrollbar-thumb {
    background-color: rgba(0, 0, 0, 0.2);
    border-radius: 4px;
}

/* Firefox scrollbar */
* {
    scrollbar-width: thin;
    scrollbar-color: rgba(0, 0, 0, 0.2) transparent;
}
</style>
