<script setup lang="ts">
import { useMouse } from "@vueuse/core";
const { x, y } = useMouse();
</script>

<template>
  <h1 class="text-3xl font-bold underline">TEST</h1>
  <div>pos: {{ x }}, {{ y }}</div>
</template>
