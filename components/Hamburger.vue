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
}
.line {
    width: 100%;
    height: 2px;
    background-color: #000;
}

.close {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
}
.menuIcon.close.line:nth-child(1) {

}
.menuIcon.close.line:nth-child(2) {
    
}
.menuIcon.close.line:nth-child(3) {
    
}

.open {
    
}
.menuIcon.open.line:nth-child(1) {

}
.menuIcon.open.line:nth-child(1) {

}
.menuIcon.open.line:nth-child(1) {

}
</style>
