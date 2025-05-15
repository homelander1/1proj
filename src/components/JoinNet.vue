<template>
    <section class="py-12 bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <!-- Section Heading -->
            <h2 class="font-bold text-center text-gray-300 flex justify-center items-center mb-12">
                <span>Join our growing network&nbsp;</span>
                <img src="../assets/images/arrowDown.png" alt="" class="w-14 h-14" />
            </h2>

            <!-- Cards Grid -->
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div v-for="item in cards" :key="item.title"
                    class="flex flex-col border-3 border-black rounded-2xl overflow-hidden">
                    <!-- Top half: icon + text -->
                    <div class="p-6 flex-1 flex flex-col">
                        <img :src="item.icon" :alt="item.title + ' icon'" class="w-6 h-6 mb-3 object-contain" />
                        <h3 class="">{{ item.title }}</h3>
                        <p class="text-gray-700 ">{{ item.description }}</p>
                        <a :href="item.link" class="mt-4 inline-flex items-center text-sm font-semibold uppercase">
                            See More&nbsp;
                            <img src="../assets/images/rightArrow.png" alt="">
                        </a>
                    </div>

                    <!-- Bottom half: image -->
                    <div class="h-50 overflow-hidden">
                        <img :src="item.image" :alt="item.title" class="w-full h-full object-cover" />
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue'

// explicitly import so bundler includes them
import img1 from '@/assets/images/card1.png'
import img2 from '@/assets/images/card2.png'
import img3 from '@/assets/images/card3.png'

import icon1 from '@/assets/images/start.png'
import icon2 from '@/assets/images/deliver.png'
import icon3 from '@/assets/images/behind.png'

const cards = ref([
    {
        icon: icon1,
        title: 'Start selling',
        description:
            'Are you a restaurant owner looking to grow your business? Reach new customers when you join our network.',
        link: '/vendors',
        image: img1,
    },
    {
        icon: icon2,
        title: 'Deliver happiness',
        description:
            'Join our elite league of delivery riders delivering happiness to customers and earn to achieve your dreams while at it.',
        link: '/riders',
        image: img2,
    },
    {
        icon: icon3,
        title: 'Behind the scenes',
        description:
            'If you are passionate about helping us achieve our goal to deliver meals seamlessly, come join the team.',
        link: '/careers',
        image: img3,
    },
])
</script>

<style scoped>
h2 {
    font-size: 66px;
    letter-spacing: -2px;
    margin-top: 30px;
    margin-bottom: 40px;
}

h3 {
    font-family: Roboto, sans-serif;
    font-weight: 700;
    font-size: 32px;
    margin-top: 18px;
    margin-bottom: 20px;
    letter-spacing: -2px;
    margin: 12px 0;

}

p {
    font-family: Roboto, sans-serif;
    font-size: 17px;
    margin-top: 8px;
    margin-bottom: 4px;
}

a {
    color: black;
    font-family: Roboto, sans-serif;
    font-size: 14px;
    font-weight: 700;
    letter-spacing: 2px;
}

a:hover {
    text-decoration: underline;
}
</style>
