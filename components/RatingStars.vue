<template>
  <div>
    <div
      v-for="(star, index) in stars"
      :key="index"
      class="inline-block">
      <div class="rating bg-yellow-300 w-8 h-8">
        <div class="star w-8 h-8"></div>
      </div>
    </div>
    
    <span class="text-sm">{{ rating.rate }}</span>
    <span class="text-sm">({{ rating.count }})</span>
  </div>
</template>

<script lang="ts" setup>
const props = defineProps<{
  rating: { rate: number; count: number };
}>();

const stars = Math.ceil(props.rating.rate);

// function applyLastStarStyling():void {
//   const lastStarEl: Element = document.getElementsByClassName('rating')[+stars];
//   const lastStarRatingEl = lastStarEl.childNodes[0] as HTMLElement;
//   const progress = props.rating.rate % 1.0;
//   lastStarRatingEl.style.width = `${progress}%`;
// }

// onMounted(() => {
//   applyLastStarStyling();
// });
</script>

<style scoped>
.star {
  content: url('../assets/svgs/star-svgrepo-com.svg');
}
</style>
