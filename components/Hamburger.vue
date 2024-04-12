<template>
    <button class="menuIcon" :class="cssClassObj" @click="toggleMenu">
        <div class="line"></div>
        <div class="line"></div>
        <div class="line"></div>
    </button>
</template>

<script lang="ts" setup>
const props = defineProps<{
    "showingMenu": boolean
}>();

const emit = defineEmits<{
  (e: 'toggle-menu'): void
}>();

function toggleMenu() {
    emit('toggle-menu');
}

const cssClassObj = computed(() => ({
  open: props.showingMenu,
  close: !props.showingMenu
}));
</script>

<style scoped>
.menuIcon {
    min-width: 30px;
    min-height: 30px;
    height: 30px;
    width: 30px;
    padding: 2px;
    overflow: hidden;
    position: relative;
}
.line {
    width: 100%;
    height: 1px;
    background-color: #000;
    transition: all 0.4s ease;
}

.menuIcon.close .line {
    margin: 5px 0;
}

.menuIcon.open .line:nth-child(1) {
    transform: rotate(-45deg);
}
.menuIcon.open .line:nth-child(2) {
    transform: rotate(45deg);
    position: relative;
    top: -1px;
}
.menuIcon.open .line:nth-child(3) {
    display: none;
}
</style>
