<template>
    <div id="Menu" v-if="showMenu" class="absolute">
        <NuxtLink
        v-for="(link, index) in menuLinks"
        :key="index"
        :to="link.href">{{ link.label }}</NuxtLink>
    </div>
</template>

<script lang="ts" setup>
defineProps<{
    showMenu: boolean;
    menuLinks: { href: string; label: string }[];
}>();
</script>

<style scoped></style>
