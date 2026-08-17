<template>
    <nav class="w-full bg-blue-600 text-white shadow-lg">
        <div class="flex items-center justify-between px-8 py-4 mx-auto">
            <div class="logo">

                <span class="md:text-2xl font-bold">Sasvata Karya Nusantara</span>
            </div>
            <div class="menu hidden md:flex items-center gap-8">
                <a href="#" class="text-sm font-medium hover:text-blue-100 transition">Home</a>
                <a href="#" class="text-sm font-medium hover:text-blue-100 transition">User Active</a>
                <a href="#" class="text-sm font-medium hover:text-blue-100 transition">Settings</a>
            </div>
            <button
                @click="isOpen = !isOpen"
                class="md:hidden text-2xl"
            >
            <transition 
            mode="out-in"
            enter-active-class="transition-opacity duration-700 ease-in"
            enter-from-class="opacity-0 scale-70"
            enter-to-class="opacity-100 scale-100"
            leave-active-class="transition-opacity duration-700 ease-out"
            leave-from-class="opacity-100 scale-70"
            leave-to-class="opacity-0 scale-100"
            
            >
                <IconMenu2 v-if="!isOpen"/>
                <IconChevronCompactDown v-else/>
            </transition>
            </button>
            
        </div>
    </nav>
    <Transition
        enter-active-class="transition-all duration-400 ease-out"
        enter-from-class="opacity-0 -translate-y-2"
        enter-to-class="opacity-100 translate-y-0"
        leave-active-class="transition-all duration-400 ease-in"
        leave-from-class="opacity-100 translate-y-0"
        leave-to-class="opacity-0 -translate-y-2"
    >
        <div
            v-if="isOpen"
            class="md:hidden flex justify-end mt-2"
        >
            <div
                class="bg-blue-500 flex flex-col gap-3 w-50 pt-4 px-6 pb-4 rounded-xl"
            >
                <a href="">Home</a>
                <a href="">Back</a>
                <a href="">Home</a>
            </div>
        </div>
    </Transition>
</template>

<script setup>
    import { ref } from 'vue'
    import {
        IconMenu2,
        IconChevronCompactDown
    } from '@tabler/icons-vue'


    const isOpen = ref(false)
    
</script>

<style lang="scss" scoped>

</style>