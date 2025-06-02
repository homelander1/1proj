<template>
    <div class="relative h-[900px]">
        <div class="w-[100%] bg-black h-[780px] absolute top-[120px] z-10"></div>
        <section class="relative  max-w-[1260px] mx-auto bg-white border-3 rounded-2xl overflow-hidden mb-4 z-20">

            <div class="flex">
                <!-- Left Column: FAQs -->
                <div class="w-[50%] flex flex-col h-[800px]">
                    <!-- Header -->
                    <div class="px-7 py-8 ">
                        <div class=" section_header text-green-800">FAQs.</div>
                    </div>
                    <!-- Questions List -->
                    <div class="flex-1 overflow-y-auto pb-4">
                        <ul class="space-y-2 pr-3 ">
                            <li v-for="(faq, idx) in faqs" :key="idx">
                                <button @click="selected = idx" :class="[
                                    'w-full text-left px-4 py-[22px] rounded flex justify-between items-center mb-3',
                                    selected === idx
                                        ? 'bg-black text-white'
                                        : 'bg-gray-50  border-gray-200 rounded-2xl border-1 text-green-800   hover:bg-green-50'
                                ]">
                                    <span class="font-medium quest">{{ faq.question }}</span>
                                    <div v-if="selected === idx" class="w-6 h-6 text-yellow-400 flex-shrink-0">
                                        <img src="../assets/images/yellow_star.svg" alt="">
                                    </div>
                                    <div v-else class="w-5 h-5"></div>
                                </button>
                            </li>
                        </ul>
                    </div>
                </div>

                <!-- Right Column: Answer -->
                <div class="w-[50%] flex flex-col h-[776px]">
                    <!-- Header -->
                    <div class="px-6 py-8">
                        <div class="section_header text-green-800">Ans.</div>
                    </div>
                    <!-- Answer Panel -->
                    <div class="px-6 h-[100%]">
                        <div class="flex-1 overflow-y-auto p-10 bg-yellow-400 border rounded-2xl h-[100%]">
                            <div class="space-y-4">
                                <div>
                                    <div class="w-6 h-6 text-yellow-900 mb-4">
                                        <img src="../assets/images/black_star.svg" alt="">
                                    </div>
                                    <p class="text-black text-base leading-relaxed question_text">
                                        {{ faqs[selected].answer }}
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

    </div>

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

<style scoped>
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

.section_header {
    font-size: 60px;
    font-weight: 800;
    font-family: 'Plus Jakarta Sans', sans-serif;
}

.question_text {
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-size: 24px;
}

.quest {
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-size: 18px;
    font-weight: 800;
}
</style>