import type { CarCard } from '#build/components';
<template>
  <div class="">
    <!-- Card -->
    <CarCard
      v-for="car in cars"
      :key="car.id"
      :car="car"
      @favor="handleFavorite"
      :favored="car.id in favorite"
    />

    <!-- Card -->
  </div>
</template>

<script setup>
const { cars } = useCar();

const favorite = useLocalStorage("favorite", {});
const handleFavorite = (id) => {
  if (id in favorite.value) {
    delete favorite.value[id];
  } else {
    favorite.value = {
      ...favorite.value,
      [id]: true,
    };
  }
};
</script>

<style lang="scss" scoped></style>
