<template>
  <div class="flex px-4">
    <div v-for="(star, index) in stars" :key="index" class="inline-block">
      <StarIcon class="w-4 h-4 text-yellow-300"></StarIcon>
    </div>

    <span>{{ rating.count + " ratings" }}</span>
  </div>
</template>

<script lang="ts" setup>
import StarIcon from './svg/StarIcon.vue';

const props = defineProps<{
  rating: { rate: number; count: number };
}>();

const stars = Math.floor(props.rating.rate);
</script>

<style scoped></style>
