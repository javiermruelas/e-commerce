<template>
  <div
    :id="productId"
    class="max-h-96 flex flex-row align-center justify-center"
  >
    <img
      :src="image"
      :alt="description"
      class="max-h-64 w-6/12 align-center justify-center"
    />
    <div
      id="productInfo"
      class="w-6/12 flex flex-col align-center justify-center"
    >
      <span class="text-xs">{{ id }}</span>
      <h1 class="text-base">{{ title }}</h1>
      <p class="text-sm">{{ description }}</p>
      <span class="text-base">{{ price }}</span>
      <p class="text-sm">
        Rated at {{ rating.rate }} stars by {{ rating.count }} users!
      </p>
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
</script>

<style scoped></style>
