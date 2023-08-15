<template>
    <header class="w-full p-2 border-b-2 flex">
      <Hamburger :menu-open="menu" v-on:toggle-menu="toggleMenu"></Hamburger>

      <nav>
        <ul>
          <NuxtLink
            v-for="(link, index) in props.headerLinks"
            :key="index"
            :to="link.href"
            >{{ link.label }}</NuxtLink
          >
        </ul>
      </nav>
    </header>
</template>

<script lang="ts" setup>
const props = defineProps<{
  headerLinks: { href: string; label: string }[];
}>();

const menu = ref(false);

function toggleMenu() {
  menu.value = !menu.value;
}
</script>

<style scoped></style>
