<template>
    <button class="menuIcon" :class="cssClassObj" @click="toggleMenu">
        <div class="line"></div>
        <div class="line"></div>
        <div class="line"></div>
    </button>
</template>

<script lang="ts" setup>
const props = defineProps<{
    "menuOpen": boolean
}>();

const emit = defineEmits<{
  (e: 'toggle-menu'): void
}>()

const cssClassObj = computed(() => ({
  open: props.menuOpen,
  close: !props.menuOpen
}));

function toggleMenu() {
    emit('toggle-menu');
}
</script>

<style scoped>
.menuIcon {
    height: 30px;
    width: 30px;
    outline: 1px solid #000;
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
