import type { CarSearchBar } from '#build/components';
<template>
  <div
    class="relative h-screen w-100 bg-no-repeat bg-cover bg-bottom bg-[url(https://images5.alphacoders.com/133/1330753.png)]"
  >
    <div class="z-10 absolute w-full h-full flex justify-center items-center">
      <div class="text-center w-1/2">
        <h1 class="text-7xl text-white font-bold mb-4">Find Your Noble Drive</h1>
        <!-- Search Bar -->
        <CarSearchBar />
        <!-- Search Bar -->
      </div>
    </div>
    <div class="z-1 absolute w-full h-full bg-black opacity-70"></div>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped></style>
