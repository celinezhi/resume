<template>
    <div class="justify-center my-1">
      <div class="text-lg flex items-center mb-1 space-x-1"><slot name="icon" /><span>{{ title }}</span></div>
      <slot />
    </div>
</template>

<script setup lang="ts">
defineProps<{ title: string }>()
</script>

<style scoped>

</style>