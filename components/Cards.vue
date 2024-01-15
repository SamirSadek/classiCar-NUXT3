import type { CarCard } from '#build/components';
<template>
  <div class="">
    <!-- Card -->
    <CarCard v-for="car in cars" :key="car.id" :car="car" />

    <!-- Card -->
  </div>
</template>

<script setup>
const { cars } = useCar();
</script>

<style lang="scss" scoped></style>
