<script setup lang="ts">
import Header from './components/Header.vue'
import Card from './components/Card.vue'
</script>

<template>
  <div class="w-4/5 m-auto bg-white min-h-dvh rounded-xl shadow-2xl mt-14">
    <Header />
    <main class="px-10 py-5">
      <section>
        <h2 class="text-3xl font-bold mb-8">Все кроссовки</h2>
        <div class="grid grid-cols-3 gap-5">
          <Card title="Sneakers nike" src="/sneakers/sneakers-1.jpg" price="1200" />
          <Card title="Sneakers nike" src="/sneakers/sneakers-1.jpg" price="1200" />
          <Card title="Sneakers nike" src="/sneakers/sneakers-1.jpg" price="1200" />
          <Card title="Sneakers nike" src="/sneakers/sneakers-1.jpg" price="1200" />
          <Card title="Sneakers nike" src="/sneakers/sneakers-1.jpg" price="1200" />
        </div>
      </section>
    </main>
  </div>
</template>

<style scoped></style>
