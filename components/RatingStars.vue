<template>
  <div class="mx-auto">
    <div
      v-for="(star, index) in stars"
      :key="index"
      class="inline-block">
      <div class="star w-8 h-8"></div>
    </div>
    
    <p class="text-center"><span class="text-sm">{{ rating.rate }}</span> <span class="text-sm">({{ rating.count }})</span></p>
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
