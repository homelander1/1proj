<template>
    <section class="py-12 bg-[#0B4228] overflow-hidden">
        <!-- Badges Row -->
        <div class="w-full overflow-hidden">
            <!-- inline-flex shrink-wraps to its children -->
            <div class="inline-flex items-center whitespace-nowrap animate-scroll-badges">
                <!-- two copies for seamless loop -->
                <template v-for="copy in 2" :key="'badges-'+copy">
                    <div v-for="badge in badges" :key="badge.label + '-' + copy"
                        class="inline-flex items-center space-x-2 bg-green-700 rounded-full text-white px-4 py-2 mx-2 whitespace-nowrap text-sm font-medium">
                        <span class="text-lg">{{ badge.icon }}</span>
                        <span>{{ badge.label }}</span>
                    </div>
                </template>
            </div>
        </div>

        <!-- Phones Row -->
        <div class="w-full overflow-hidden mt-6">
            <div class="inline-flex items-center whitespace-nowrap animate-scroll-phones">
                <template v-for="copy in 2" :key="'phones-'+copy">
                    <div v-for="(img, idx) in phoneImages" :key="idx + '-' + copy" class="inline-block mx-4">
                        <div class="w-40 h-96 bg-white rounded-3xl border-4 border-green-900 overflow-hidden">
                            <img :src="img" alt="phone screenshot" class="w-full h-full object-cover" />
                        </div>
                    </div>
                </template>
            </div>
        </div>
    </section>
</template>

<script setup>
const badges = [
    { icon: '🌟', label: 'Quick & easy onboarding' },
    { icon: '🍽️', label: 'Quality meal choices' },
    { icon: '✨', label: 'Live updates on orders' },
    { icon: '📍', label: 'Highly rated riders' },
    { icon: '⏱️', label: '24/7 support for customers and vendors' },
]

const phoneImages = [
    '/images/phone1.png',
    '/images/phone2.png',
    '/images/phone3.png',
    '/images/phone4.png',
    '/images/phone5.png',
]
</script>

<style>
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

/* Shrink-wrapped inline-flex is exactly 2× content width,
   so translating -50% shifts out one full set of items */
.animate-scroll-badges {
    animation: scroll-badges 25s linear infinite;
}

.animate-scroll-phones {
    animation: scroll-phones 40s linear infinite;
}
</style>
