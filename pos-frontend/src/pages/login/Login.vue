<template>
  <div class="w-full max-w-md">
    <h1 class="text-4xl font-bold text-gray-800 mb-2">Welcome back!</h1>
    <p class="text-gray-700 text-sm mb-8">
      Doesn't have an account? 
      <button @click="$emit('switch')" class="underline font-semibold hover:text-black">
        create ann account
      </button> 
      now to get full access
    </p>

    <form @submit.prevent class="space-y-4">
      <div>
        <label class="block text-xs font-semibold text-gray-800 mb-1">Email</label>
        <input type="email" class="w-full px-4 py-2 bg-transparent text-gray-900 border border-gray-400 rounded-md focus:outline-none focus:border-[#052b14]" />
      </div>

      <div>
        <label class="block text-xs font-semibold text-gray-800 mb-1">Password</label>
        <div class="relative">
          <input :type="showPassword ? 'text' : 'password'" class="w-full px-4 py-2 pr-10 bg-transparent text-gray-900 border border-gray-400 rounded-md focus:outline-none focus:border-[#052b14]" />
          
          <button type="button" @click="showPassword = !showPassword" class="absolute inset-y-0 right-0 flex items-center pr-3 text-gray-500 hover:text-gray-700">
            <svg v-if="showPassword" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M2 12s3-7 10-7 10 7 10 7-3 7-10 7-10-7-10-7Z"/>
              <circle cx="12" cy="12" r="3"/>
            </svg>
            
            <svg v-else xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M9.88 9.88a3 3 0 1 0 4.24 4.24"/>
              <path d="M10.73 5.08A10.43 10.43 0 0 1 12 5c7 0 10 7 10 7a13.16 13.16 0 0 1-1.67 2.68"/>
              <path d="M6.61 6.61A13.526 13.526 0 0 0 2 12s3 7 10 7a9.74 9.74 0 0 0 5.39-1.61"/>
              <line x1="2" x2="22" y1="2" y2="22"/>
            </svg>
          </button>
        </div>
      </div>

      <div class="flex justify-start">
        <a href="#" class="text-xs font-semibold text-gray-800 hover:underline">
          Forget password? click here to get help
        </a>
      </div>

      <div class="pt-2 space-y-3">
        <button class="w-full bg-[#092c15] border-[3px] border-[#0c66e4] text-white font-semibold py-2 rounded-md hover:bg-[#061d0e] transition">
          Login now
        </button>
        <button type="button" class="w-full bg-transparent border border-gray-400 text-gray-900 font-semibold py-2.5 rounded-md flex items-center justify-center gap-2 hover:bg-gray-50 transition">
          <span class="font-bold text-lg">G</span> Login with Google
        </button>
      </div>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const showPassword = ref(false)
</script>