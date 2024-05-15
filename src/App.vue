<script setup>
import { onMounted, ref } from 'vue'
import axios from 'axios'

import Header from './components/Header.vue'
import CardList from './components/CardList.vue'

const items = ref([])

onMounted(async () => {
  try {
    const { data } = await axios.get('https://6d5d58cbb6bda4ee.mokky.dev/items')
    items.value = data
  } catch (error) {
    console.log(error)
  }
})
</script>

<template>
  <!-- <Drawer /> -->
  <div class="w-4/5 m-auto bg-white min-h-dvh rounded-xl shadow-2xl mt-14">
    <Header />
    <main class="px-10 py-5">
      <section>
        <CardList title="Все кроссовки" :items="items" />
      </section>
    </main>
  </div>
</template>

<style scoped></style>
