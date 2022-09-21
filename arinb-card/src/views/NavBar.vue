<script setup>
let isOpen = $ref(false)
</script>

<template>
  <header class="bg-gray-900 sm:flex sm:justify-between sm:items-center">
    <div class="flex justify-between items-center  px-4 py-3">
      <div>
        <img class="h-8" src="../assets/logo-inverted.svg" alt="">
      </div>
      <div class="sm:hidden">
        <button
            class="transition-colors h-8 text-gray-400 outline-none border px-1 py-.5 border-gray-600 rounded hover:text-gray-100 hover:border-gray-400"
            @click="isOpen = !isOpen"
        >
          <svg class="h-6 w-6 fill-current" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
               stroke-width="1.5" stroke="currentColor"
          >
            <path v-if="!isOpen" stroke-linecap="round" stroke-linejoin="round"
                  d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"/>
            <path v-if="isOpen" stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12"/>
          </svg>
        </button>
      </div>
    </div>
    <!-- mobile menu -->
    <div
        :class="isOpen ? 'flex': 'hidden'"
        class="px-2 pt-2 flex pb-4 flex-col sm:flex sm:flex-row"
    >
      <a href="#" class="transition-colors text-gray-100 px-2.5 py-2 rounded-lg hover:bg-gray-800">Messages</a>
      <a href="#" class="transition-colors text-gray-100 px-2.5 py-2 rounded-lg hover:bg-gray-800">Contact Us</a>
      <a href="#" class="transition-colors text-gray-100 px-2.5 py-2 rounded-lg hover:bg-gray-800">Contact Us</a>
    </div>
  </header>
</template>