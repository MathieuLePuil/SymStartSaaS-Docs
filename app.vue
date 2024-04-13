<template>
    <nav>
        <div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8">
            <div class="relative flex h-24 items-center justify-between sm:mx-20">
                <div class="inset-y-0 left-0 flex items-center sm:hidden">
                    <button @click="toggleMobileMenu" :aria-expanded="menuOpen.toString()" type="button" class="button ml-5" aria-controls="mobile-menu">
                        <svg class="block h-6 w-6" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"></path>
                        </svg>
                        <svg class="hidden h-6 w-6" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12"></path>
                        </svg>
                    </button>
                </div>
                <div class="flex flex-1 items-center justify-center sm:items-stretch sm:justify-start">
                    <div class="flex flex-shrink-0 items-center">
                        <img class="h-8 w-auto" src="/public/logo-symstartsaas.png" alt="CodeClipper Logo">
                    </div>
                    <div class="hidden sm:flex sm:ml-6 sm:justify-end flex-1">
                        <div class="flex space-x-4">
                            <a href="" class="text-light-text dark:text-dark-text rounded-md px-3 py-2 ml-10 text-ml font-medium font-body hover:underline hover:scale-105 transition-all duration-200 ease" aria-current="page">Home</a>
                            <a href="" class="text-light-text dark:text-dark-text rounded-md px-3 py-2 text-ml font-medium font-body hover:bg-light-primary dark:hover:bg-dark-primary hover:text-light-background dark:hover:text-dark-background hover:underline hover:scale-105 transition-all duration-200 ease" aria-current="page">Docs</a>
                            <a href="" class="text-light-text dark:text-dark-text rounded-md px-3 py-2 text-ml font-medium font-body hover:bg-light-primary dark:hover:bg-dark-primary hover:text-light-background dark:hover:text-dark-background hover:underline hover:scale-105 transition-all duration-200 ease" aria-current="page">GitHub</a>
                        </div>
                    </div>
                </div>
                <div class="h-6 w-0.5 bg-gray-800 dark:bg-gray-100 hidden md:block ml-3"></div>
                <div class="flex items-center mr-6 sm:static sm:inset-auto sm:ml-6 sm:pr-0">
                    <button @click="toggleTheme" class="toggle-mode">
                        <div class="ml-4 md:ml-0 border-[1px] rounded border-solid p-1 border-black dark:border-white" :class="{'border-light-text': !isDark, 'border-dark-text': isDark}">
                            <svg v-if="isDark" class="w-[16px] h-[16px] text-gray-800 dark:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="currentColor" viewBox="0 0 24 24">
                                <path fill-rule="evenodd" d="M11.675 2.015a.998.998 0 0 0-.403.011C6.09 2.4 2 6.722 2 12c0 5.523 4.477 10 10 10 4.356 0 8.058-2.784 9.43-6.667a1 1 0 0 0-1.02-1.33c-.08.006-.105.005-.127.005h-.001l-.028-.002A5.227 5.227 0 0 0 20 14a8 8 0 0 1-8-8c0-.952.121-1.752.404-2.558a.996.996 0 0 0 .096-.428V3a1 1 0 0 0-.825-.985Z" clip-rule="evenodd"/>
                            </svg>

                            <svg v-else class="w-[16px] h-[16px] text-gray-800 dark:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="currentColor" viewBox="0 0 24 24">
                                <path fill-rule="evenodd" d="M13 3a1 1 0 1 0-2 0v2a1 1 0 1 0 2 0V3ZM6.343 4.929A1 1 0 0 0 4.93 6.343l1.414 1.414a1 1 0 0 0 1.414-1.414L6.343 4.929Zm12.728 1.414a1 1 0 0 0-1.414-1.414l-1.414 1.414a1 1 0 0 0 1.414 1.414l1.414-1.414ZM12 7a5 5 0 1 0 0 10 5 5 0 0 0 0-10Zm-9 4a1 1 0 1 0 0 2h2a1 1 0 1 0 0-2H3Zm16 0a1 1 0 1 0 0 2h2a1 1 0 1 0 0-2h-2ZM7.757 17.657a1 1 0 1 0-1.414-1.414l-1.414 1.414a1 1 0 1 0 1.414 1.414l1.414-1.414Zm9.9-1.414a1 1 0 0 0-1.414 1.414l1.414 1.414a1 1 0 0 0 1.414-1.414l-1.414-1.414ZM13 19a1 1 0 1 0-2 0v2a1 1 0 1 0 2 0v-2Z" clip-rule="evenodd"/>
                            </svg>
                        </div>
                    </button>
                </div>
            </div>
        </div>

        <div :class="{'hidden': !menuOpen}" id="mobile-menu">
            <div class="space-y-1 px-2 pb-3 pt-2">
                <a href="" class="block text-light-text dark:text-dark-text rounded-md px-3 py-2 text-ml font-medium font-body hover:bg-light-primary dark:hover:bg-dark-primary hover:text-light-background dark:hover:text-dark-background -mt-6" aria-current="page">Home</a>
                <a href="" class="block text-light-text dark:text-dark-text rounded-md px-3 py-2 text-ml font-medium font-body hover:bg-light-primary dark:hover:bg-dark-primary hover:text-light-background dark:hover:text-dark-background" aria-current="page">Docs</a>
                <a href="" class="block text-light-text dark:text-dark-text rounded-md px-3 py-2 text-ml font-medium font-body hover:bg-light-primary dark:hover:bg-dark-primary hover:text-light-background dark:hover:text-dark-background border-b-2 border-dark-text border-solid" aria-current="page">GitHub</a>
            </div>
        </div>
    </nav>

    <NuxtPage />
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue';

const menuOpen = ref(false);
const isDark = ref(true);

function toggleMobileMenu() {
    menuOpen.value = !menuOpen.value;
}

function closeMenuOnClickOutside(event) {
    const menuButton = document.querySelector('.button');
    const menu = document.getElementById('mobile-menu');
    if (menuOpen.value && !menu.contains(event.target) && !menuButton.contains(event.target)) {
        menuOpen.value = false;
    }
}

function loadTheme() {
    const storedTheme = localStorage.getItem('theme');
    if (storedTheme) {
        document.documentElement.classList.add(storedTheme);
        isDark.value = storedTheme === 'dark';
    }
}

function toggleTheme() {
    isDark.value = !isDark.value;
    const theme = isDark.value ? 'dark' : 'light';
    document.documentElement.classList.toggle('dark', isDark.value);
    localStorage.setItem('theme', theme);
}

onMounted(() => {
    loadTheme();
    document.addEventListener('click', closeMenuOnClickOutside);
});

onBeforeUnmount(() => {
    document.removeEventListener('click', closeMenuOnClickOutside);
});
</script>


