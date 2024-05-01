<script setup>
import { useHead } from '@vueuse/head'

useHead({
    title: 'SymStartSaaS: Your SaaS Boilerplate',
    link: [
        { rel: 'icon', type: 'image/png', href: '/logo-symstartsaas.png' }
    ],
    meta: [
        { charset: 'utf-8' },
        { name: 'viewport', content: 'width=device-width, initial-scale=1.0' }
    ]
})
</script>

<template>
    <main class="w-full flex flex-col items-center justify-center pb-[96px] space-y-5 sm:space-y-10" style="height: calc(100vh - 96px); font-family: Inter, sans-serif">
        <div class="flex flex-col items-center space-y-2">
            <h3 class="font-bold text-3xl md:text-6xl">Your Symfony</h3>
            <h2 class="font-bold text-3xl md:text-6xl text-blue-600 dark:text-blue-400">SaaS Boilerplate</h2>
        </div>
        <p class="block sm:hidden w-[90%] sm:w-[70%] text-xs sm:text-md text-center text-gray-500 dark:text-gray-400">SymStartSaaS is a Symfony project base with elements such as Tailwind, user management, account creation with GitHub, Google or Discord and payment via Stripe.</p>
        <p class="hidden sm:block w-[70%] text-xs sm:text-md text-center text-gray-500 dark:text-gray-400">SymStartSaaS is a Symfony project base with elements such as Tailwind, <br> user management, account creation with GitHub, Google or Discord and payment via Stripe.</p>
        <div class="sm:space-x-10 space-y-4 sm:space-y-0 scale-75 sm:scale-100 flex flex-col sm:flex-row items-center justify-center">
            <a href="https://github.com/MathieuLePuil/SymStartSaaS/blob/main/README.md" target="_blank" class="p-3 bg-blue-600 dark:bg-blue-400 rounded text-white dark:text-black hover:bg-blue-500 dark:hover:bg-blue-300 transition-all duration-200 ease">
                <Icon name="uil:rocket" class="text-white dark:text-black mb-1" />
                Get Started
            </a>
            <a href="https://youtu.be/a0VAMdXpZho" target="_blank" class="p-3 border border-blue-600 dark:border-blue-400 rounded text-black dark:text-white hover:bg-gray-100 dark:hover:bg-gray-800 transition-all duration-200 ease">
                <Icon name="uil:play" class="dark:text-white text-black mb-1" />
                How install SymStartSaaS ?
            </a>
        </div>
    </main>
</template>

<style scoped>

</style>