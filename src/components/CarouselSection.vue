<template>
    <div class="relative h-[900px]">
        <div class="w-[100%] h-[780px] absolute top-[120px] z-10 back"></div>
        <div class="carousel_block relative  z-20">
            <div class="rounded-2xl overflow-hidden w-310 mx-auto relative">
                <!-- Slides Container -->
                <div class="w-full h-196">
                    <div v-for="(slide, idx) in slides" :key="idx" v-show="currentIndex === idx"
                        class="w-full h-full flex flex-col items-center justify-start text-black"
                        :style="{ backgroundColor: slide.backgroundColor }">
                        <h2 class="text-4xl font-extrabold text-center mb-6">
                            {{ slide.title }}
                        </h2>
                        <img :src="slide.image" alt="" class="h-140 w-270 mb-4" />
                    </div>
                </div>

                <!-- Pagination at bottom-left -->
                <div class="absolute bottom-5 left-5 flex items-center space-x-2">
                    <button v-for="(_, idx) in slides" :key="idx" @click="goTo(idx)"
                        class="m-1 relative rounded-full flex items-center justify-center overflow-visible"
                        :style="buttonStyle(idx)">
                        <img v-if="getButtonIcon(idx)" :src="getButtonIcon(idx)" alt="" class="w-8 h-8" />
                        <span v-else class="text-lg font-medium leading-none">
                            {{ slides[idx].label }}
                        </span>
                        <!-- Progress ring -->
                        <svg v-if="currentIndex === idx" class="absolute inset-0" viewBox="0 0 56 56">
                            <circle cx="28" cy="28" r="27" fill="none" stroke-width="3" :stroke="currentScheme[idx]"
                                :stroke-dasharray="circumference" :stroke-dashoffset="dashOffset"
                                style="transform: rotate(-90deg); transform-origin: 28px 28px;" />
                        </svg>
                    </button>
                </div>

                <!-- Arrows at bottom-right -->
                <div class="absolute bottom-5 right-5 flex items-center space-x-2">
                    <button @click="prevSlide" :style="arrowStyle()"
                        class="w-10 h-10 rounded-full flex items-center justify-center">
                        <img :src="getRightArrow()" alt="Prev" class="w-6 h-6" />
                    </button>
                    <button @click="nextSlide" :style="arrowStyle()"
                        class="m-2 w-10 h-10 rounded-full flex items-center justify-center">
                        <img :src="getLeftArrow()" alt="Next" class="w-6 h-6" />
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, computed, onMounted, onBeforeUnmount, watch } from 'vue';

// slide main images
import img0 from '@/assets/images/african-meals.svg';
import img1 from '@/assets/images/Fastfoodxsnacks.svg';
import img2 from '@/assets/images/drink.svg';
import img3 from '@/assets/images/Fitfam.svg';
import img4 from '@/assets/images/Pack.svg';

// per-slide pagination icons
import map1 from '@/assets/images/map1.svg';
import star1 from '@/assets/images/star1.svg';
import map2 from '@/assets/images/map2.svg';
import star2 from '@/assets/images/star2.svg';
import map3 from '@/assets/images/map3.svg';
import star3 from '@/assets/images/star3.svg';
import map4 from '@/assets/images/map4.svg';
import star4 from '@/assets/images/star4.svg';
import map5 from '@/assets/images/map5.svg';
import star5 from '@/assets/images/star5.svg';

// per-slide arrow icons
import la1 from '@/assets/images/la1.svg';
import la2 from '@/assets/images/la2.svg';
import la3 from '@/assets/images/la3.svg';
import la4 from '@/assets/images/la4.svg';
import la5 from '@/assets/images/la5.svg';
import ra1 from '@/assets/images/ra1.svg';
import ra2 from '@/assets/images/ra2.svg';
import ra3 from '@/assets/images/ra3.svg';
import ra4 from '@/assets/images/ra4.svg';
import ra5 from '@/assets/images/ra5.svg';

// Slides data
const slides = ref([
    { image: img0, title: 'Get started in 3', backgroundColor: '#038B5C', label: null },
    { image: img1, title: 'Download the app', backgroundColor: '#8C77EC', label: '01' },
    { image: img2, title: 'Explore categories', backgroundColor: '#FFC501', label: '02' },
    { image: img3, title: 'Place your orders', backgroundColor: '#FF884D', label: '03' },
    { image: img4, title: 'Enjoy your meal', backgroundColor: '#FFEDB3', label: null },
]);

// Pagination icon sets
const buttonIconSets = [
    { first: map1, last: star1 },
    { first: map2, last: star2 },
    { first: map3, last: star3 },
    { first: map4, last: star4 },
    { first: map5, last: star5 },
];

// Arrow icon arrays
const leftArrows = [la1, la2, la3, la4, la5];
const rightArrows = [ra1, ra2, ra3, ra4, ra5];

const currentIndex = ref(0);

function getButtonIcon(idx) {
    if (idx === 0) return buttonIconSets[currentIndex.value].first;
    if (idx === slides.value.length - 1) return buttonIconSets[currentIndex.value].last;
    return null;
}

function getLeftArrow() {
    return leftArrows[currentIndex.value];
}

function getRightArrow() {
    return rightArrows[currentIndex.value];
}

// Color schemes & progress
const colorSchemes = [
    ['#02C27F', '#02C27F', '#02C27F', '#02C27F', '#02C27F'],
    ['#FFD1E2', '#FFD1E2', '#FFD1E2', '#FFD1E2', '#FFD1E2'],
    ['#000000', '#000000', '#000000', '#000000', '#000000'],
    ['#0C513F', '#0C513F', '#0C513F', '#0C513F', '#0C513F'],
    ['#ED5E3B', '#ED5E3B', '#ED5E3B', '#ED5E3B', '#ED5E3B'],
];
const duration = 5000, tick = 50;
const progressValue = ref(0);
let intervalId;
const radius = 27;
const circumference = 2 * Math.PI * radius;
const dashOffset = computed(() => circumference * (1 - progressValue.value / 100));
const currentScheme = computed(() => colorSchemes[currentIndex.value]);

function startTimer() {
    clearInterval(intervalId);
    progressValue.value = 100;
    intervalId = setInterval(() => {
        progressValue.value = Math.max(0, progressValue.value - (tick / duration) * 100);
        if (progressValue.value <= 0) nextSlide();
    }, tick);
}

function nextSlide() {
    currentIndex.value = (currentIndex.value + 1) % slides.value.length;
}

function prevSlide() {
    currentIndex.value = (currentIndex.value - 1 + slides.value.length) % slides.value.length;
}

function goTo(idx) {
    currentIndex.value = idx;
}

function buttonStyle(idx) {
    const fill = currentScheme.value[idx];
    const currentBg = slides.value[currentIndex.value].backgroundColor;
    return {
        backgroundColor: currentIndex.value === idx ? 'transparent' : fill,
        color: currentIndex.value === idx ? fill : currentBg,
    };
}

function arrowStyle() {
    const fill = currentScheme.value[currentIndex.value];
    return { backgroundColor: fill, color: '#ffffff' };
}

watch(currentIndex, startTimer);
onMounted(startTimer);
onBeforeUnmount(() => clearInterval(intervalId));
</script>

<style scoped>
button {
    width: 56px;
    height: 56px;
    border-radius: 50%;
}

h2 {
    font-family: Roboto, sans-serif;
    font-weight: 700;
    font-size: 70px;
    letter-spacing: -3px;
    margin-top: 50px;
    margin-bottom: 30px;
}

.back {
    background-color: #0C513F;
}
</style>
