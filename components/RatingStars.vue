<template>
  <div class="flex px-4">
    <div
      v-for="(star, index) in stars"
      :key="index"
      class="inline-block">
      <div class="star w-8 h-8"></div>
    </div>
    
    <span>{{ rating.count + ' ratings' }}</span>
  </div>
</template>

<script lang="ts" setup>
const props = defineProps<{
  rating: { rate: number; count: number };
}>();

const stars = Math.floor(props.rating.rate);
</script>

<style scoped>
.star {
  content: url('../assets/svgs/star-svgrepo-com.svg');
}
</style>
