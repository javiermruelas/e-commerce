<template>
  <div
    :id="productId"
    class="shadow-sm bg-neutral-100 p-2 grid grid-cols-2 gap-4 rounded"
  >
    <img :src="image" :alt="description" class="w-max h-max" />
    <div id="productInfo" class="flex flex-col align-center justify-center">
      <h1 class="text-base">{{ title }}</h1>
      <p class="text-sm">{{ shortenedDesc }}</p>
      <span class="text-base">{{ '$' + price }}</span>
      <RatingStars :rating="rating" />
      <span class="text-xs">{{ category.toUpperCase() }}</span>
    </div>
  </div>
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
