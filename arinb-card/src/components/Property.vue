<script setup>
const {property} = defineProps(['property'])
</script>

<template>
  <div class="bg-white border rounded-lg overflow-hidden">
    <img :src="property.image_url" :alt="property.image_alt">
    <div class="p-6">
      <div class="text-gray-600 text-xs uppercase tracking-wide ">
        {{ property.beds }} beds &bull; {{ property.baths }} baths
      </div>
      <div class="mt-2 text-lg font-semibold text-gray-600 leading-tight ">{{ property.title }}</div>
      <div class="mt-2 tracking-wide text-gray-700">
        {{ property.formatted_price }}
        <span class="text-gray-500">/ wk</span>
      </div>
      <div class="mt-4 text-gray-800 tracking-wide">
        <span class="text-teal-600 text-lg font-semibold">{{ property.rating }}/5 stars</span>
        <span class="ml-2 text-gray-500">(base on {{ property.review_count }} reviews)</span>
      </div>
    </div>
  </div>
</template>