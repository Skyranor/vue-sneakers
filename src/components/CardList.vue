<script setup>
import Card from './Card.vue'
defineProps({
  title: String,
  items: Array
})
</script>

<template>
  <section class="flex flex-col gap-5">
    <h2 class="text-3xl font-bold mb-8">{{ title }}</h2>
    <ul class="grid grid-cols-3 gap-5">
      <Card
        v-for="item in items"
        :key="item.id"
        :price="item.price"
        :title="item.title"
        :imgUrl="item.imageUrl"
      />
    </ul>
  </section>
</template>
