<script setup>
import starIcon from '@/assets/images/card1.png'
import badgeIcon from '@/assets/images/card1.png'
import logo from '@/assets/images/card1.png'
import twitterIcon from '@/assets/images/card1.png'
import facebookIcon from '@/assets/images/card1.png'
import instagramIcon from '@/assets/images/card1.png'
import linkedinIcon from '@/assets/images/card1.png'
</script>

<template>
    <footer class="bg-black text-white">
        <!-- Subscription row -->
        <div
            class="max-w-[1248px] mx-auto px-4 lg:px-0 flex flex-col lg:flex-row items-center justify-between py-8 border-b border-gray-800">
            <div class="flex items-center space-x-3 mb-6 lg:mb-0">
                <img :src="starIcon" alt="Star" class="h-6 w-6" />
                <h3 class="text-2xl font-bold">Cool stuff only</h3>
                <span class="text-sm text-gray-400">Subscribe to our newsletter</span>
            </div>
            <form class="flex items-center w-full lg:w-auto">
                <input type="email" placeholder="yourname@email.com"
                    class="flex-grow bg-transparent placeholder-gray-500 border-b border-gray-700 focus:outline-none text-sm py-2 mr-4" />
                <button type="submit" class="p-2">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor"
                        class="w-6 h-6 text-purple-500">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                            d="M13 7l5 5m0 0l-5 5m5-5H6" />
                    </svg>
                </button>
            </form>
        </div>

        <!-- Links grid -->
        <div
            class="max-w-[1248px] mx-auto px-4 lg:px-0 grid grid-cols-2 lg:grid-cols-4 gap-8 py-8 border-b border-gray-800">
            <div class="flex justify-center lg:justify-start">
                <img :src="badgeIcon" alt="Badge" class="w-16 h-16" />
            </div>

            <!-- Company links -->
            <div>
                <h4 class="text-gray-400 font-semibold mb-4 uppercase">Company</h4>
                <ul class="space-y-2 text-sm">
                    <li><a href="#" class="hover:text-white">Customers</a></li>
                    <li><a href="#" class="hover:text-white">Vendors</a></li>
                    <li><a href="#" class="hover:text-white">Riders</a></li>
                    <li><a href="#" class="hover:text-white">Storefront</a></li>
                    <li><a href="#" class="hover:text-white">About</a></li>
                    <li><a href="#" class="hover:text-white">Careers</a></li>
                    <li><a href="#" class="hover:text-white">FAQs</a></li>
                    <li><a href="#" class="hover:text-white">Blog</a></li>
                    <li><a href="#" class="hover:text-white">Contact</a></li>
                    <li><a href="#" class="hover:text-white">Terms of Use</a></li>
                    <li><a href="#" class="hover:text-white">Privacy Policy</a></li>
                </ul>
            </div>

            <!-- Cuisines near you -->
            <div>
                <h4 class="text-gray-400 font-semibold mb-4 uppercase">Cuisines Near You</h4>
                <ul class="space-y-2 text-sm">
                    <li><a href="#" class="hover:text-white">Pasta near me</a></li>
                    <li><a href="#" class="hover:text-white">Rice near me</a></li>
                    <li><a href="#" class="hover:text-white">Fast food near me</a></li>
                    <li><a href="#" class="hover:text-white">Asian food in Lagos</a></li>
                    <li><a href="#" class="hover:text-white">African food in Lagos</a></li>
                    <li><a href="#" class="hover:text-white">Breakfast menu in Lagos</a></li>
                    <li><a href="#" class="hover:text-white">Fiftam stores in Lagos</a></li>
                    <li><a href="#" class="hover:text-white">American food in Lagos</a></li>
                    <li><a href="#" class="hover:text-white">Pastries in Lagos</a></li>
                    <li><a href="#" class="hover:text-white">Salad in Lagos</a></li>
                    <li><a href="#" class="hover:text-white">Fruits in Lagos</a></li>
                </ul>
            </div>

            <!-- Popular links -->
            <div>
                <h4 class="text-gray-400 font-semibold mb-4 uppercase">Popular</h4>
                <ul class="space-y-2 text-sm">
                    <li><a href="#" class="hover:text-white">Food delivery</a></li>
                    <li><a href="#" class="hover:text-white">Surulere</a></li>
                    <li><a href="#" class="hover:text-white">Ogudu</a></li>
                    <li><a href="#" class="hover:text-white">Yaba</a></li>
                    <li><a href="#" class="hover:text-white">Ikeja</a></li>
                    <li><a href="#" class="hover:text-white">Lekki</a></li>
                    <li><a href="#" class="hover:text-white">King Glab</a></li>
                    <li><a href="#" class="hover:text-white">Korede Spaghetti</a></li>
                    <li><a href="#" class="hover:text-white">Iyan Aladuke</a></li>
                    <li><a href="#" class="hover:text-white">Food Fusion</a></li>
                    <li><a href="#" class="hover:text-white">Belefull</a></li>
                </ul>
            </div>
        </div>

        <!-- Bottom row -->
        <div class="max-w-[1248px] mx-auto px-4 lg:px-0 flex flex-col lg:flex-row items-center justify-between py-8">
            <!-- Logo -->
            <div class="mb-6 lg:mb-0">
                <img :src="logo" alt="Chowdeck" class="h-8" />
            </div>

            <!-- Social links grid -->
            <div class="grid grid-cols-2 sm:grid-cols-4 gap-x-12 gap-y-6 text-sm">
                <!-- Twitter -->
                <a href="#" class="flex items-center space-x-2 hover:text-white">
                    <img :src="twitterIcon" alt="Twitter" class="h-5 w-5" />
                    <span>Twitter</span>
                </a>
                <!-- Instagram -->
                <a href="#" class="flex items-center space-x-2 hover:text-white">
                    <img :src="instagramIcon" alt="Instagram" class="h-5 w-5" />
                    <span>Instagram</span>
                </a>
                <!-- Facebook -->
                <a href="#" class="flex items-center space-x-2 hover:text-white">
                    <img :src="facebookIcon" alt="Facebook" class="h-5 w-5" />
                    <span>Facebook</span>
                </a>
                <!-- LinkedIn -->
                <a href="#" class="flex items-center space-x-2 hover:text-white">
                    <img :src="linkedinIcon" alt="LinkedIn" class="h-5 w-5" />
                    <span>LinkedIn</span>
                </a>
            </div>
        </div>
    </footer>
</template>

<style scoped>
/* Hide default input underline on WebKit but keep the bottom border */
input::-webkit-appearance {
    -webkit-appearance: none;
}
</style>