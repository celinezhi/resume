<template>
    <p>• {{ content }}</p>
</template>

<script setup lang="ts">
defineProps<{content: string}>()
</script>

<style scoped></style>