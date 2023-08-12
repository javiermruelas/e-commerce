<template>
  <p>Products Page!</p>
  <div class="w-full flex flex-col justify-between align-center">
    <ProductCard
      v-for="(product, index) in products"
      :key="index"
      v-bind="product"
    >
    </ProductCard>
  </div>
</template>

<script lang="ts" setup>
// const {data: products} = await useFetch('https://fakestoreapi.com/products');
const { data: products } = await useFetch(
  "https://fakestoreapi.com/products/1",
);

console.log("Products: ", products.value);
</script>
