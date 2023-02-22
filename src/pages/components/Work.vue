<template>
  <Block>
    <div class="flex justify-between font-bold text-xl">
      <div>{{ title }}</div>
      <div>{{ dateText }}</div>
    </div>
    <div v-for="{ title, items }, idx in projects" :key="idx" class="border-t-2 my-2 pt-2">
        <p v-if="title" class="font-bold">{{ title }}</p>
        <Item v-for="item, iidx in items" :key="`${idx}_${iidx}`" :content="item" />
    </div>
  </Block>
</template>

<script setup lang="ts">
import Block from './Block.vue';
import Item from './Item.vue';
import { computed } from 'vue'
const { date } = defineProps<{
    title: string;
    date: string[];
    projects: {
        title?: string;
        items: string[];
    }[];
}>()
const dateText = computed(() => {
    const [start, end = '至今'] = date
    return [start, end].join(' - ')
})
</script>

<style scoped>

</style>