<template>
  <a href="#" class="block group">
    <div
    :id="productId"
    class="shadow-sm bg-neutral-100 p-2 grid rounded"
  >
    <img :src="image" :alt="description" class="object-cover w-full rounded aspect-square" />
    <div id="productInfo" class="flex flex-col align-center justify-center">
      <h1 class="text-lg font-bold">{{ '$' + price }}</h1>
      <h2 class="text-base font-bold">{{ title }}</h2>
      <p class="text-sm font-light">{{ shortenedDesc }}</p>
      <RatingStars :rating="rating" />
      <span class="text-xs">{{ category.toUpperCase() }}</span>
    </div>
  </div>
  </a>
</template>

<script lang="ts" setup>
const props = defineProps<{
  id: number;
  title: string;
  description: string;
  price: number;
  rating: { rate: number; count: number };
  image: string;
  category: string;
}>();
const productId = `product-${props.id}`;
const descCharLimit = 45;
const shortenedDesc = props.description.length > 20 ? props.description.slice(0, descCharLimit) + '...' : props.description;
</script>

<style scoped></style>
