<template>
    <div class="restaurants">

        <div class="max-w-[1250px] mx-auto bg-white border-3 border-black rounded-3xl overflow-hidden flex h-[800px]">
            <!-- Left: static map image -->
            <div class="w-2/3 border-r-3 border-black-800 relative">
                <img src="../assets/images/LiveLocationBG.svg" alt="Map" class="w-full h-full object-cover" />
                <div class="absolute top-35 left-35">
                    <a href=""><img src="../assets/images/Ogudu_e1552ab64b.png.png" alt=""></a>
                </div>
                <div class="absolute top-75 left-25">
                    <a href=""><img src="../assets/images/Yaba_91670ee055.png.png" alt=""></a>
                </div>
                <div class="absolute top-45 left-135">
                    <a href=""><img src="../assets/images/Surulere_77593861c4.png.png" alt=""></a>
                </div>
                <div class="absolute top-120 left-95">
                    <a href=""><img src="../assets/images/Ikeja_2dd3121b42.png.png" alt=""></a>
                </div>
                <div class="absolute top-135 left-135">
                    <a href=""><img src="../assets/images/Lekki_657afbc50f.png.png" alt=""></a>
                </div>
                <img class="absolute top-[680px] left-[150px]" src="../assets/images/clickany.png" alt="">

            </div>

            <!-- Right: scrollable list -->
            <div class="w-[540px] flex flex-col">
                <!-- Header -->
                <div class="bg-blue-300 px-4 py-3 border-b-4 border-black flex items-center">
                    <img class="inline-block " src="../assets/images/circle_before.png" alt="">
                    <h3 class="text-lg font-semibold text-black ml-2 m-0 px-2 py-1.5">Restaurants</h3>
                </div>

                <!-- Scrollable list -->
                <div class="flex-1 overflow-y-auto bg-white">
                    <ul class="p-3">
                        <li v-for="item in items" :key="item.name" class="mb-2 ">
                            <a :href="item.link"
                                class="flex justify-between items-center bg-white rounded-lg border border-gray-200 px-3 py-3 rest-button">
                                <span class="text-gray-800 ">{{ item.name }}</span>
                                <div class="bg-gray-100 rounded-full p-2 flex items-center justify-center">
                                    <img src="../assets/images/cart.png" alt="">
                                </div>

                            </a>
                        </li>
                    </ul>
                </div>
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

<style scoped>
.rest-button:hover {
    background-color: #f4f4f4;
}

/* Webkit browsers (Chrome, Edge, Safari) */
::-webkit-scrollbar {
    width: 24px;
    /* Wide scrollbar track */
    background: transparent;
}

::-webkit-scrollbar-track {
    background: #f4f4f4;
    /* Track color: very light gray */
    border-radius: 12px;
}

::-webkit-scrollbar-thumb {
    background: #fff;
    /* Thumb color: white */
    border-radius: 12px;
    /* Fully rounded ends */
    border: 6px solid #f4f4f4;
    /* Creates 'padding' around thumb */
    min-height: 56px;
    /* Nice tall thumb */
    box-shadow: 0 1px 4px rgba(0, 0, 0, 0.07);
    /* Very subtle shadow (optional) */
}

/* For Firefox */
* {
    scrollbar-width: thin;
    /* Makes the thumb narrower */
    scrollbar-color: #fff #f4f4f4;
    /* Thumb color (white) and track color */
}
</style>
