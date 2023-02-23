<template>
    <div class="justify-center my-5">
      <div class="text-xl flex items-center mb-1"><slot name="icon" />{{ title }}</div>
      <slot />
    </div>
</template>

<script setup lang="ts">
defineProps<{ title: string }>()
</script>

<style scoped>

</style>