<script setup>
import {onBeforeMount, onMounted, onUnmounted} from "vue";

const isOpen = $ref(false);

onMounted(() => {
  const handleEscape = (evt) => {
    if (evt.key === 'Esc' || evt.key === 'Escape') {
      isOpen = false;
    }
  }

  document.addEventListener('keydown', handleEscape)

  onUnmounted(() => {
    document.removeEventListener('keydown', handleEscape)
  })
})
</script>


<template>
  <div class="relative">
    <button @click="isOpen = !isOpen" class="block w-8 h-8  border-2 border-gray-300 rounded-full overflow-hidden">
      <img
          class="relative z-10 h-full w-full object-cover object-center"
          src="https://images.unsplash.com/photo-1532074205216-d0e1f4b87368?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=441&q=80"
          alt="Girl who's looking to the right side">
    </button>
    <button v-if="isOpen" @click="isOpen = false"
            tabindex="-1"
            class="fixed inset-0 min-h-screen w-full h-full bg-black/10 cursor-default"></button>
    <div v-if="isOpen" class="absolute right-0 w-48 mt-1 py-3 flex flex-col bg-white  rounded-lg shadow-xl">
      <a class="transition-colors duration-300 px-4 py-1 text-gray-800 hover:bg-indigo-600 hover:text-white" href="#">Account
        setting</a>
      <a class="transition-colors duration-300 px-4 py-1 text-gray-800 hover:bg-indigo-600 hover:text-white" href="#">Messages</a>
      <a class="transition-colors duration-300 px-4 py-1 text-gray-800 hover:bg-indigo-600 hover:text-white" href="#">Logout</a>
    </div>
  </div>
</template>
