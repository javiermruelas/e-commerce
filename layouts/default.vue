<template>
  <div class="bg-neutral-50">
    <MenuComponent :show-menu="showMenu" :menu-links="menuLinks"></MenuComponent>
    <HeaderComponent :header-links="headerLinks" v-on:toggle-menu="toggleMenu" :showing-menu="showMenu"></HeaderComponent>
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

const menuLinks = [
  { href: "/products", label: "Products" },
  { href: "/sign-in", label: "Sign In" },
  { href: "/cart", label: "Cart" },
];

const showMenu = ref(false);
function toggleMenu() {
  showMenu.value = !showMenu.value;
}
</script>

<style scoped></style>
