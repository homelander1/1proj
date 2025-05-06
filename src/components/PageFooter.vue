<script setup>
const currentYear = new Date().getFullYear()
</script>

<template>
    <link rel="stylesheet" href="footer.css">

    <footer class="bg-black text-white text-sm pt-10">
        <div class="container mx-auto px-4 flex flex-col lg:flex-row justify-between">

            <!-- Left Section -->
            <div class="flex flex-col gap-6">
                <img src="../assets/images/badge.svg" alt="Badge" class="w-20" />
                <a href="mailto:yourname@email.com" class="text-gray-400 hover:text-white">yourname@email.com</a>
            </div>

            <!-- Middle Sections -->
            <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8 mt-10 lg:mt-0">
                <div>
                    <h3 class="font-semibold uppercase text-gray-400 mb-3">Company</h3>
                    <ul class="space-y-1">
                        <li><a href="/">customers</a></li>
                        <li><a href="/vendors">Vendors</a></li>
                        <li><a href="/riders">Riders</a></li>
                        <li><a href="/store" target="_blank" rel="noreferrer">Storefront</a></li>
                        <li><a href="/company">About</a></li>
                        <li><a href="https://chowdeck.bamboohr.com/careers" target="_blank" rel="noreferrer">Careers</a>
                        </li>
                        <li><a href="/#faqs">FAQs</a></li>
                        <li><a href="/blog">Blog</a></li>
                        <li><a href="/contact">Contact</a></li>
                        <li><a href="/terms">Terms of Use</a></li>
                        <li><a href="/privacy">Privacy Policy</a></li>
                    </ul>
                </div>

                <div>
                    <h3 class="font-semibold uppercase text-gray-400 mb-3">Cuisines near you</h3>
                    <ul class="space-y-1">
                        <li><a href="/store/cuisines/pasta-near-me">Pasta near me</a></li>
                        <li><a href="/store/cuisines/rice-near-me">Rice near me</a></li>
                        <li><a href="/store/cuisines/fast-food-near-me">Fast food near me</a></li>
                        <li><a href="/store/cuisines/asian-food-in-lagos">Asian food in Lagos</a></li>
                        <li><a href="/store/cuisines/african-food-in-lagos">African food in Lagos</a></li>
                        <li><a href="/store/cuisines/breakfast-menu-in-lagos">Breakfast menu in Lagos</a></li>
                        <li><a href="/store/cuisines/fitfam-stores-in-lagos">Fitfam stores in Lagos</a></li>
                        <li><a href="/store/cuisines/american-food-in-lagos">American food in Lagos</a></li>
                        <li><a href="/store/cuisines/pastries-in-lagos">Pastries in Lagos</a></li>
                        <li><a href="/store/cuisines/salad-in-lagos">Salad in Lagos</a></li>
                        <li><a href="/store/cuisines/fruits-in-lagos">Fruits in Lagos</a></li>
                    </ul>
                </div>

                <div>
                    <h3 class="font-semibold uppercase text-gray-400 mb-3">Popular</h3>
                    <ul class="space-y-1">
                        <li><a href="/store">Food delivery</a></li>
                        <li><a href="/store/surulere">Surulere</a></li>
                        <li><a href="/store/ogudu">Ogudu</a></li>
                        <li><a href="/store/lagos-mainland">Yaba</a></li>
                        <li><a href="/store/ikeja">Ikeja</a></li>
                        <li><a href="/store/lekki">Lekki</a></li>
                        <li><a href="/store/ikeja/restaurants/king-glab-ikeja">King Glab</a></li>
                        <li><a href="/store/lagos-mainland/restaurants/korede-spaghetti">Korede Spaghetti</a></li>
                        <li><a href="/store/lagos-mainland/restaurants/iyan-aladuke">Iyan Aladuke</a></li>
                        <li><a href="/store/ikeja/restaurants/food-fusion-lagos">Food Fusion</a></li>
                        <li><a href="/store/ikeja/restaurants/belefull">Belefull</a></li>
                    </ul>
                </div>
            </div>
        </div>

        <!-- Social Links -->
        <div class="container mx-auto px-4 mt-10 mb-6 flex flex-wrap gap-4 justify-center text-center text-white">
            <a href="https://twitter.com/chowdeck" target="_blank" rel="noreferrer">✨ Twitter</a>
            <a href="https://www.instagram.com/chowdeck/" target="_blank" rel="noreferrer">🌸 Instagram</a>
            <a href="https://facebook.com/chowdeck" target="_blank" rel="noreferrer">🟣 Facebook</a>
            <a href="https://www.linkedin.com/company/chowdeck/" target="_blank" rel="noreferrer">🟠 LinkedIn</a>
        </div>

        <!-- Copyright -->
        <div class="text-center text-gray-500 pb-6">
            <p>© All Rights Reserved. {{ currentYear }}, Chowdeck Logistics Inc.</p>
        </div>
    </footer>
</template>

<style scoped>
.navigation-footer {
    background-color: #000;
    color: #fff;
    padding: 40px 0 20px 0;
    font-size: 14px;
}

.navigation-footer .sunscribe-email {
    display: flex;
    justify-content: flex-end;
    padding: 0 5%;
    margin-bottom: 30px;
}

.sunscribe-email input {
    background: transparent;
    border: none;
    border-bottom: 1px solid #ccc;
    color: #fff;
    padding: 8px;
    margin-right: 10px;
    width: 200px;
}

.sunscribe-email button {
    background-color: transparent;
    color: #a68eff;
    border: none;
    font-size: 18px;
    cursor: pointer;
    transform: rotate(-45deg);
    margin-top: -5px;
}

.footexr-flex {
    display: flex;
    flex-wrap: wrap;
    padding: 0 5%;
    gap: 40px;
}

.footer-logos {
    display: flex;
    flex-direction: column;
    gap: 30px;
    min-width: 100px;
}

.company-section,
.cuisine-section,
.popular-section {
    min-width: 160px;
}

.footer-list {
    list-style: none;
    padding: 0;
    margin: 0;
}

.footer-list li {
    margin-bottom: 10px;
}

.footer-list a {
    color: #ccc;
    text-decoration: none;
    transition: color 0.3s ease;
}

.footer-list a:hover {
    color: #fff;
}

h3 {
    font-size: 14px;
    font-weight: 600;
    text-transform: uppercase;
    color: #aaa;
    margin-bottom: 12px;
}

.social-links {
    margin-top: 40px;
    display: flex;
    flex-direction: column;
    gap: 12px;
}

.social-links ul {
    list-style: none;
    padding: 0;
    margin: 0;
}

.social-links li {
    margin-bottom: 10px;
}

.social-links a {
    display: flex;
    align-items: center;
    color: #ccc;
    text-decoration: none;
}

.social-links a:hover {
    color: #fff;
}

.social-links img {
    width: 18px;
    height: 18px;
    margin-right: 10px;
}

footer>div:last-child {
    text-align: center;
    padding-top: 20px;
    color: #666;
    font-size: 13px;
}

/* Responsive behavior */
@media (max-width: 768px) {
    .footexr-flex {
        flex-direction: column;
    }

    .sunscribe-email {
        justify-content: center;
        padding: 0 20px;
    }

    .social-links {
        align-items: center;
    }
}
</style>