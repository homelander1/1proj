<template>
    <section class="py-16 bg-[#0C513F] overflow-hidden">

        <div class="overflow-hidden  ">
            <ul class="flex gap-4 animate-scroll-badges">
                <li v-for="(badge, i) in badges" :key="i"
                    class="flex items-center text-white py-[10px] px-3 rounded-[6px] gap-3 whitespace-nowrap"
                    style="background-color: rgba(255,255,255,0.1); border: 1px solid rgba(255,255,255,0.1);">
                    <span class="w-6 h-5 flex-shrink-0 flex items-center justify-center">
                        <img :src="badge.icon" alt="" class="w-full h-full object-contain" />
                    </span>
                    <span class="feature">{{ badge.label }}</span>
                </li>
            </ul>
        </div>


        <div class="overflow-hidden">
            <div class="phone flex items-start gap-6 animate-scroll-phones ">
                <template v-for="copy in 2" :key="'phones-'+copy">
                    <div v-for="(phone, idx) in phoneImages" :key="idx + '-' + copy" class="flex-shrink-0 w-84"
                        :style="{ marginTop: phone.mt }">
                        <img :src="phone.src" alt="phone screenshot" class="w-full h-auto object-cover" />
                    </div>
                </template>
            </div>
        </div>
    </section>
</template>

<script setup>
import img0 from '@/assets/images/accept-order.png'
import img1 from '@/assets/images/order-arrived.png'
import img2 from '@/assets/images/order-transit.png'
import img3 from '@/assets/images/pickup.png'

import bg1 from '@/assets/images/Vector.svg'
import bg2 from '@/assets/images/Vector (1).svg'
import bg3 from '@/assets/images/Vector (2).svg'
import bg4 from '@/assets/images/Vector (3).svg'
import bg5 from '@/assets/images/Vector (4).svg'



const badges = [
    { icon: bg1, label: 'Quick and easy onboarding' },
    { icon: bg2, label: 'Quality meal choices' },
    { icon: bg3, label: 'Live updates on orders' },
    { icon: bg4, label: 'Highly rated riders' },
    { icon: bg5, label: '24/7 support for customers and vendors' },
    { icon: bg1, label: 'Quick and easy onboarding' },
    { icon: bg2, label: 'Quality meal choices' },
    { icon: bg3, label: 'Live updates on orders' },
    { icon: bg4, label: 'Highly rated riders' },
    { icon: bg5, label: '24/7 support for customers and vendors' },

]


const phoneImages = [
    { src: img0, mt: '0px' },
    { src: img1, mt: '20px' },
    { src: img2, mt: '0px' },
    { src: img3, mt: '20px' },
    { src: img0, mt: '0px' },
    { src: img1, mt: '20px' },
    { src: img2, mt: '0px' },
    { src: img3, mt: '20px' },
]
</script>

<style scoped>
.feature {
    font-size: 16px;
    font-weight: 500;
}

.phone {
    margin-top: 60px;
}

@keyframes scroll-badges {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(-50%);
    }
}

@keyframes scroll-phones {
    from {
        transform: translateX(0);
    }

    to {
        transform: translateX(-50%);
    }
}

.animate-scroll-badges {
    animation: scroll-badges 15s linear infinite;
}

.animate-scroll-phones {
    animation: scroll-phones 20s linear infinite;
}
</style>
