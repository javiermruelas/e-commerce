<template>
    <header class="w-full h-20 p-2 border-b-2 flex items-center sticky top-0 bg-neutral-100">
      <Hamburger :showing-menu="showingMenu" v-on:toggle-menu="toggleMenu"></Hamburger>

      <nav class="w-full flex items-center">
        <ul class="w-full flex justify-end items-center">
          <NuxtLink
            v-for="(link, index) in props.headerLinks"
            :key="index"
            :to="link.href"
            class="mx-2"
            >
            <span v-if="link.label === 'Products'" :class="labelCss">{{ link.label }}</span>
            <PersonIcon v-if="link.label === 'Sign In'" :class="iconCss"></PersonIcon>
            <CartIcon v-if="link.label === 'Cart'" :class="iconCss"></CartIcon>
          </NuxtLink>
        </ul>
      </nav>
    </header>
</template>

<script lang="ts" setup>
import PersonIcon from './svg/PersonIcon.vue';
import CartIcon from './svg/CartIcon.vue';
const iconCss = "w-6 h-6 object-cover aspect-square";
const labelCss = "";

const props = defineProps<{
  headerLinks: { href: string; label: string }[];
  showingMenu: boolean;
}>();

const emit = defineEmits<{
  (e: 'toggle-menu'): void
}>();

function toggleMenu() {
  emit('toggle-menu');
}
</script>

<style scoped></style>
