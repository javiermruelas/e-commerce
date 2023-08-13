<template>
  <div class="bg-neutral-50">
    <header>
      <nav>
        <ul>
          <NuxtLink
            v-for="(link, index) in headerLinks"
            :key="index"
            :to="link.href"
            >{{ link.label }}</NuxtLink
          >
        </ul>
      </nav>
    </header>
    <slot />
    <footer>
      <nav></nav>
    </footer>
  </div>
</template>

<script lang="ts" setup>
const headerLinks = [
  { href: "/products", label: "Products" },
  { href: "/sign-in", label: "Sign In" },
  { href: "/account-settings", label: "Account Settings" },
  { href: "/cart", label: "Cart" }
];
</script>
