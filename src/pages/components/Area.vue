<template>
    <div class="justify-center my-5">
      <div><slot name="icon" />{{ title }}</div>
      <slot />
    </div>
</template>

<script setup lang="ts">
defineProps<{ title: string }>()
</script>

<style scoped>

</style>