<template>
  <div class="bg-neutral-50">
    <HeaderComponent :header-links="headerLinks"></HeaderComponent>
    <slot />
    <FooterComponent></FooterComponent>
  </div>
</template>

<script lang="ts" setup>
const headerLinks = [
  { href: "/products", label: "Products" },
  { href: "/sign-in", label: "Sign In" },
  { href: "/cart", label: "Cart" },
];
</script>

<style scoped></style>
