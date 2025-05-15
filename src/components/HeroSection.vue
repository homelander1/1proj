<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import PageHeader from '@/components/PageHeader.vue'

const phrases = [
    'Have you eaten?',
    'Have you?',
    'Still Hungry?'
]

const msg = ref(phrases[0])

let intervalId = null

onMounted(() => {
    let i = 0
    intervalId = setInterval(() => {
        msg.value = phrases[i]
        i = (i + 1) % phrases.length
    }, 2000)
})

onUnmounted(() => {
    clearInterval(intervalId)
})
</script>

<template>
    <div class="hero-wrapper">
        <PageHeader class="absolute inset-x-0 top-10 w-full z-10" />

        <div class="hero-content">
            <img class="cloud1" src="../assets/images/cloud1.svg" alt="">
            <img class="cloud2" src="../assets/images/cloud2.svg" alt="">
            <img class="cloud3" src="../assets/images/bcloud.svg" alt="">
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
            <img class="lr-ryder-1 absolute top-[1090px] -left-20" src="../assets/images/lr ryder1.png" alt="">
            <img class="rl-ryder-1 absolute top-[1030px] right-20" src="../assets/images/rl ryder1.png" alt="">
            <img class="diagonalRyder absolute top-[860px] -right-20" src="../assets/images/diagonalRyder.png" alt="">

        </div>
        <img class="bottom-clouds" src="../assets/images/bottom clouds-4.svg" alt="">

    </div>
</template>

<style scoped>
.bottom-clouds {
    z-index: 99;
    margin-top: 595px;
}


.hero-wrapper {

    height: 1200px;

    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;

    overflow: hidden;

    background-image:
        url('../assets/images/hebg.svg');
    background-position:
        center center,
        center center;
    background-size:
        auto,
        contain;
    background-repeat:
        no-repeat,
        no-repeat;
}

.hero-content {
    display: flex;
    flex-direction: column;

    align-items: center;
}


.cloud1,
.cloud2,
.cloud3 {
    position: absolute;
    transform-origin: center center;
    will-change: transform;
}

.lr-ryder-1 {
    animation: ryder-1 16s linear infinite
}

@keyframes ryder-1 {
    0% {
        transform: translate(0, 0) rotate(0deg);
    }

    100% {
        transform: translate(3000px, 0) rotate(0deg);
    }
}



.rl-ryder-1 {

    animation: ryder-rtl 12s linear infinite;
}

@keyframes ryder-rtl {


    0% {
        transform: translateX(1000px) rotate(0deg);
    }


    100% {
        transform: translateX(-3000px) rotate(0deg);
    }
}

.diagonalRyder {

    animation: diagonalRyderl 8s linear infinite;
}

@keyframes diagonalRyderl {

    0% {
        transform: translateX(300px) translateY(-150px) rotate(0deg);
    }


    100% {
        transform: translateX(-1900px) translateY(550px) rotate(0deg);
    }
}




.cloud1 {
    top: -60px;

    left: 10%;
    animation: float-1 6s ease-in-out infinite;
}

.cloud2 {
    top: -80px;

    right: 10%;
    animation: float-2 8s ease-in-out infinite;
}

.cloud3 {

    z-index: 10;
    top: 380px;
    right: -100px;


    animation: float-3 4s ease-in-out infinite;
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


@keyframes float-3 {
    0% {
        transform: translate(0, 0) rotate(0deg);
    }

    50% {
        transform: translate(-200px, 0) rotate(0deg);
    }

    100% {
        transform: translate(0, 0) rotate(0deg);
    }
}

h1 {
    color: black;
    font-weight: 700;
    font-size: 112px;
    margin-top: 180px;
    margin-bottom: 20px;
    letter-spacing: -6px;
    font-family: 'Roboto', sans-serif;
}

.app-store {
    display: inline-flex;
    align-items: center;
    background-color: #0C513F;
    color: white;
    padding: 18px 26px;
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
