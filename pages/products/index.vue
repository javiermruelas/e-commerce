<template>
  <p>Products Page!</p>
  <div class="container mx-auto px-4 grid gap-y-4">
    <ProductCard
      v-for="(product, index) in products"
      :key="index"
      v-bind="product"
    >
    </ProductCard>
  </div>
</template>

<script lang="ts" setup>
const { data: products } = await useFetch("https://fakestoreapi.com/products");

console.log("Products: ", products.value);
</script>
