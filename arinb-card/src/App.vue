<script setup>
import PropertyCard from "./components/Property.vue";

const property = {
  image_url: "https://images.unsplash.com/photo-1600596542815-ffad4c1539a9?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1175&q=80",
  image_alt: "Rear view of modern house with pool",
  beds: 3,
  baths: 2,
  title: "Modern home in city center ",
  price_in_cent: "1900000",
  formatted_price: "$1,900,00",
  review_count: 34,
  rating: 4,
}
</script>

<template>
  <main class="antialiased text-gray-900 bg-gray-300 min-h-screen grid place-items-center p-8 ">
    <PropertyCard :property="property"/>
  </main>
</template>

