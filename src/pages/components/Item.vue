<template>
    <p class="text-sm">• {{ content }}</p>
</template>

<script setup lang="ts">
defineProps<{content: string}>()
</script>

<style scoped></style>