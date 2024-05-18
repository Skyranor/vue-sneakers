<script setup>
import { onMounted, reactive, ref, watch } from 'vue'
import axios from 'axios'

import Header from './components/Header.vue'
import CardList from './components/CardList.vue'

const items = ref([])
const filters = reactive({
  sortBy: 'title',
  searchQuery: ''
})

const fetchItems = async () => {
  try {
    const params = {
      sortBy: filters.sortBy
    }

    if (filters.searchQuery) {
      params.title = `*${filters.searchQuery}*`
    }

    const { data } = await axios.get(`https://6d5d58cbb6bda4ee.mokky.dev/items`, {
      params
    })

    items.value = data
  } catch (err) {
    console.log(err)
  }
}

onMounted(async () => {
  await fetchItems()
})

watch(filters, fetchItems)
</script>

<template>
  <!-- <Drawer /> -->
  <div class="w-4/5 m-auto bg-white min-h-dvh rounded-xl shadow-2xl mt-14">
    <Header />
    <main class="px-10 py-5">
      <div class="flex gap-4">
        <select v-model="filters.sortBy" class="py-2 px-3 border rounded-md outline-none">
          <option value="title">По названию</option>
          <option value="price">По цене (дешевые)</option>
          <option value="-price">По цене (дорогие)</option>
        </select>

        <div class="relative">
          <img class="absolute left-4 top-3" src="/search.svg" />
          <input
            class="border rounded-md py-2 pl-11 pr-4 outline-none focus:border-gray-400"
            type="text"
            placeholder="Поиск..."
            v-model="filters.searchQuery"
          />
        </div>
      </div>

      <section>
        <CardList title="Все кроссовки" :items="items" />
      </section>
    </main>
  </div>
</template>

<style scoped></style>
