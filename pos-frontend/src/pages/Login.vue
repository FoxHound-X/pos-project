<script setup>
import { ref } from 'vue'
import SidePanel from './Login/Side.vue'
import LoginForm from './Login/Login.vue'
import RegisterForm from './Login/Register.vue'
const isRegister = ref(true)
</script>

<template>
  <div class="min-h-screen flex bg-[#f2f2f2] font-sans">
    <div class="hidden lg:block lg:w-[45%]">
      <SidePanel />
    </div>

    <div class="w-full lg:w-[55%] flex flex-col p-8 lg:p-16 relative">
      <div class="absolute top-8 left-8 lg:top-12 lg:left-16">
        <h2 class="text-xl font-bold text-gray-900">Eternal Project</h2>
      </div>

      <div class="flex-1 flex items-center justify-center overflow-hidden">
        
        <Transition name="slide-fade" mode="out-in">
          <RegisterForm v-if="isRegister" @switch="isRegister = false" />
          <LoginForm v-else @switch="isRegister = true" />
        </Transition>
        
      </div>
    </div>
  </div>
</template>

<style scoped>
.slide-fade-enter-active,
.slide-fade-leave-active {
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.slide-fade-enter-from {
  opacity: 0;
  transform: translateY(30px);
}

.slide-fade-leave-to {
  opacity: 0;
  transform: translateY(-30px);
}
</style>



