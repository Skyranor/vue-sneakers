<script setup lang="ts"></script>

<template>
  <header class="flex justify-between border-b-2 border-slate-300 px-10 py-8">
    <div class="flex gap-4 items-center">
      <img class="w-10 h-10" src="/logo.png" alt="logo" />
      <div>
        <h2 class="text-xl font-bold uppercase">Vue Sneakers</h2>
        <span class="text-slate-400"> Магазин лучших кроссовок</span>
      </div>
    </div>
    <ul class="flex items-center justify-between gap-10">
      <li>
        <a class="flex gap-2 text-gray-500 hover:text-black cursor-pointer"
          ><img src="/cart.svg" alt="cart" /> <b>1205 руб.</b></a
        >
      </li>
      <li>
        <a class="flex gap-2 text-gray-500 hover:text-black cursor-pointer">
          <img src="/heart.svg" alt="favorite" /> <span> Закладки</span></a
        >
      </li>
      <li>
        <a class="flex gap-2 text-gray-500 hover:text-black cursor-pointer">
          <img src="/profile.svg" alt="profile" /> <span> Профиль</span></a
        >
      </li>
    </ul>
  </header>
</template>
