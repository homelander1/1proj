<template>
    <section class="max-w-5xl mx-auto bg-white border border-black rounded-2xl overflow-hidden">
        <div class="flex">
            <!-- Left Column: FAQs -->
            <div class="w-1/3 border-r border-gray-200 flex flex-col h-[600px]">
                <!-- Header -->
                <div class="px-6 py-8">
                    <h3 class="text-3xl font-bold text-green-800">FAQs.</h3>
                </div>
                <!-- Questions List -->
                <div class="flex-1 overflow-y-auto px-4 pb-4">
                    <ul class="space-y-2">
                        <li v-for="(faq, idx) in faqs" :key="idx">
                            <button @click="selected = idx" :class="[
                                'w-full text-left px-6 py-4 rounded flex justify-between items-center transition-colors duration-200',
                                selected === idx
                                    ? 'bg-black text-white'
                                    : 'bg-white text-green-800 hover:bg-green-50'
                            ]">
                                <span class="font-medium">{{ faq.question }}</span>
                                <svg v-if="selected === idx" class="w-5 h-5 text-yellow-400 flex-shrink-0"
                                    fill="currentColor" viewBox="0 0 24 24">
                                    <path
                                        d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z" />
                                </svg>
                                <div v-else class="w-5 h-5"></div>
                            </button>
                        </li>
                    </ul>
                </div>
            </div>

            <!-- Right Column: Answer -->
            <div class="w-2/3 flex flex-col h-[600px]">
                <!-- Header -->
                <div class="px-6 py-8 bg-yellow-400">
                    <h3 class="text-3xl font-bold text-green-800">Ans.</h3>
                </div>
                <!-- Answer Panel -->
                <div class="flex-1 overflow-y-auto p-6 bg-yellow-400">
                    <div class="space-y-4">
                        <div class="flex items-start space-x-4">
                            <svg class="w-6 h-6 text-yellow-900 flex-shrink-0" fill="currentColor" viewBox="0 0 24 24">
                                <path
                                    d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z" />
                            </svg>
                            <p class="text-black text-base leading-relaxed">
                                {{ faqs[selected].answer }}
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref } from 'vue'

const faqs = ref([
    { question: 'What is Chowdeck?', answer: 'Chowdeck is a technology company that provides logistics services to both vendors and consumers. This potentially allows food vendors to deliver meals seamlessly while also providing consumers with an easy platform to order meals from their favourite restaurants in their city.' },
    { question: 'How do I sign up as a vendor on Chowdeck?', answer: 'To sign up as a vendor, visit our vendor registration page, fill out your business details, upload required documents, and submit. Our team will review and activate your vendor account within 48 hours.' },
    { question: 'How do I create an account on Chowdeck?', answer: 'Download the Chowdeck app or visit chowdeck.com and click on Sign Up. Enter your phone number or email, create a password, and verify your account to start ordering.' },
    { question: 'What is Chowdeck wallet?', answer: 'Chowdeck Wallet is a secure in-app wallet that lets you store funds for faster checkout, manage refunds, and track your spending on our platform.' },
    { question: 'What is Chowscore?', answer: 'Chowscore is our loyalty program where you earn points for every order. Points can be redeemed for discounts, free deliveries, and exclusive offers.' },
    { question: 'What is Service fee?', answer: 'The Service fee covers payment processing, platform maintenance, and customer support, ensuring a reliable and seamless experience.' },
    { question: 'Why do we charge Service fee?', answer: 'Charging a Service fee allows us to invest in our infrastructure, support vendors, and offer 24/7 customer service.' },
    { question: 'How can I track my order?', answer: 'Once your order is placed, you can track it in real-time via the app. You’ll see updates when the restaurant accepts, when the rider picks up, and when they’re en route.' },
    { question: 'Can I preorder meals?', answer: 'Yes, if the restaurant offers a preorder option, you can select a future time for delivery or pickup during checkout.' },
    { question: 'What payment methods are accepted?', answer: 'We accept credit/debit cards, mobile wallets, and cash on delivery in select regions.' },
    { question: 'How do I apply a promo code?', answer: 'During checkout, enter your promo code in the designated field and click Apply. The discount will reflect in your order total.' },
    { question: 'Can I schedule a delivery?', answer: 'Yes, for supported restaurants you can choose a delivery window up to 24 hours in advance.' },
    { question: 'What happens if my order is late?', answer: 'If your order is delayed, our support team will notify you and offer a voucher or refund depending on the situation.' },
    { question: 'How do I contact support?', answer: 'In the app, go to Support → Contact Us or email support@chowdeck.com. We’re available 24/7.' },
    { question: 'How do I delete my account?', answer: 'To delete your account, navigate to Settings → Account → Delete Account. Follow the prompts to confirm deletion.' }
])

const selected = ref(0)
</script>

<style>
/* Scrollbar Styling */
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

/* Firefox */
* {
    scrollbar-width: thin;
    scrollbar-color: rgba(0, 0, 0, 0.2) transparent;
}
</style>