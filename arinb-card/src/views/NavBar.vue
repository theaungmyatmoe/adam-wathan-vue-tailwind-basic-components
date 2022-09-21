<script setup>
import DropDown from '../components/DropDown.vue'

let isOpen = $ref(false)
</script>

<template>
  <header
      class="sticky  top-0 bg-gray-900 backdrop-filter bg-opacity-90 backdrop-blur-sm sm:flex sm:justify-between sm:items-center sm:px-10 ">
    <div class="flex justify-between items-center  px-4 py-3">
      <div>
        <img class="h-8" src="../assets/logo-inverted.svg" alt="">
      </div>
      <div class="sm:hidden">
        <!--        nav toggler -->
        <button
            class="transition-colors h-8 px-1 text-gray-400 outline-none border border-gray-600 rounded hover:text-gray-100 hover:border-gray-400"
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
        class="px-2 pt-2 flex pb-4 flex-col sm:flex sm:flex-row sm:gap-x-4 sm:items-center"
    >
      <a href="#" class="transition-colors text-gray-100 px-2.5 py-2 rounded-lg hover:bg-gray-800">Messages</a>
      <a href="#" class="transition-colors text-gray-100 px-2.5 py-2 rounded-lg hover:bg-gray-800">Contact Us</a>
      <a href="#" class="transition-colors text-gray-100 px-2.5 py-2 rounded-lg hover:bg-gray-800">Contact Us</a>
      <!--      account dropdown for desktop-->
      <DropDown class="hidden sm:block"/>

      <div class="mt-2 p-2 py-4  border-t border-gray-700 sm:hidden">
        <button class="mx-2">
          <img
              class=" w-8 h-8  border-2 border-gray-500 rounded-full object-cover object-center"
              src="https://images.unsplash.com/photo-1532074205216-d0e1f4b87368?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=441&q=80"
              alt="Girl who's looking to the right side">
        </button>
        <!--        account setting -->
        <div v-if="isOpen" class="flex flex-col">
          <a class="transition-colors duration-300 px-2 py-2 text-gray-100 hover:bg-gray-800 hover:text-white rounded-lg"
             href="#">Account
            setting</a>
          <a class="transition-colors duration-300 px-2 py-2 text-gray-100 hover:bg-gray-800 hover:text-white rounded-lg"
             href="#">Messages</a>
          <a class="transition-colors duration-300 px-2 py-2 text-gray-100 hover:bg-gray-800 hover:text-white rounded-lg"
             href="#">Logout</a>
        </div>
      </div>

    </div>
  </header>
</template>