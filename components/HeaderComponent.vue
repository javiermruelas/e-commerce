<template>
    <header>
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
</script>
