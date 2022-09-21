<script setup>
const {property} = defineProps(['property'])
</script>

<template>
  <div>
    <div class="relative bg-red-500 pb-[calc(100%/4*3)] rounded-lg">
      <img class="absolute h-full w-full object-cover object-center rounded-lg" :src="property.image_url"
           :alt="property.image_alt">
    </div>
    <div class="relative px-4 -mt-16">
      <div class="bg-white p-6 rounded-lg shadow-lg">
        <div class="flex items-baseline gap-x-2">
        <span
            class="inline-block uppercase text-xs bg-teal-600/60 px-2.5 py-1 text-teal-900 rounded-full font-semibold">New</span>
          <div class="text-gray-600 text-xs uppercase tracking-wide ">
            {{ property.beds }} beds &bull; {{ property.baths }} baths
          </div>
        </div>
        <div class="mt-1 text-lg font-semibold text-gray-600 leading-tight ">{{ property.title }}</div>
        <div class="mt-2 tracking-wide text-gray-700">
          {{ property.formatted_price }}
          <span class="text-gray-500">/ wk</span>
        </div>
        <div class="flex items-center mt-4 text-gray-800 tracking-wide">
          <svg v-for="i in 5" class="h-5" :class="i <= property.rating ? 'text-teal-500/90' : 'text-gray-200'"
               xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor">
            <path fill-rule="evenodd"
                  d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.007 5.404.433c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.433 2.082-5.006z"
                  clip-rule="evenodd"/>
          </svg>

          <span class="ml-2 text-gray-500">{{ property.review_count }} reviews</span>
        </div>
      </div>
    </div>
  </div>
</template>