<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import PageHeader from '@/components/PageHeader.vue'

const phrases = [
    'Have you eaten?',
    'Second Have you eaten?',
    'Third Have you eaten?'
]

// msg is reactive so template updates when its value changes
const msg = ref(phrases[0])

let intervalId = null

onMounted(() => {
    let i = 0
    intervalId = setInterval(() => {
        msg.value = phrases[i]
        i = (i + 1) % phrases.length
    }, 2000) // change phrase every 2s
})

onUnmounted(() => {
    clearInterval(intervalId)
})
</script>

<template>
    <div class="hero-wrapper">
        <PageHeader />
        <img class="cloud1" src="../assets/images/cloud1.svg" alt="">
        <img class="cloud2" src="../assets/images/cloud2.svg" alt="">
        <h1>{{ msg }}</h1>
        <div>
            <a href="" class="app-store">
                <img src="../assets/images/image (23).svg" alt="Google Play Logo" />
                <span>Download on Google Play</span>
            </a>
            <a href="" class="app-store">
                <img src="../assets/images/Group 49.svg" alt="Apple Store Logo" />
                <span>Download on Apple Store</span>
            </a>
        </div>
    </div>
</template>

<style scoped>
.hero-wrapper {

    height: 1024px;
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    /* clip any cloud parts that stick out */
    overflow: hidden;

    /* background layers */
    background-image:
        url('../assets/images/bottom couds.svg'),
        url('../assets/images/hebg.svg');
    background-position:
        center center,
        center center;
    background-size:
        contain,
        cover;
    background-repeat:
        no-repeat,
        no-repeat;
}

/* common for both clouds */
.cloud1,
.cloud2 {
    position: absolute;
    transform-origin: center center;
    will-change: transform;
}

/* push them above the top edge */
.cloud1 {
    top: -60px;
    /* adjust this to taste */
    left: 10%;
    animation: float-1 6s ease-in-out infinite;
}

.cloud2 {
    top: -80px;
    /* adjust this to taste */
    right: 10%;
    animation: float-2 8s ease-in-out infinite;
}

@keyframes float-1 {
    0% {
        transform: translate(0, 0) rotate(0deg);
    }

    25% {
        transform: translate(55px, -10px) rotate(0deg);
    }

    50% {
        transform: translate(70px, -20px) rotate(0deg);
    }

    75% {
        transform: translate(-105px, -10px) rotate(0deg);
    }

    100% {
        transform: translate(0, 0) rotate(0deg);
    }
}

@keyframes float-2 {
    0% {
        transform: translate(0, 0) rotate(0deg);
    }

    25% {
        transform: translate(-100px, 10px) rotate(-4deg);
    }

    50% {
        transform: translate(300px, 20px) rotate(0deg);
    }

    75% {
        transform: translate(100px, 10px) rotate(4deg);
    }

    100% {
        transform: translate(0, 0) rotate(0deg);
    }
}

h1 {
    color: black;
}

.app-store {
    display: inline-flex;
    align-items: center;
    background-color: rgb(14, 90, 14);
    color: white;
    padding: 12px 24px;
    margin: 0 6px;
    border-radius: 6px;
    font-family: sans-serif;
    gap: 8px;
    text-decoration: none;
}

.app-store img {
    height: 20px;
    width: auto;
    display: block;
}
</style>
