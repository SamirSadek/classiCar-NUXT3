<template>
  <div>
    <div class="max-w-7xl mx-auto">
      <div class="mt-16 flex">
        <!-- Side Bar -->
        <CarSideBar />
        <!-- Side Bar -->

        <NuxtPage />
      </div>
    </div>
  </div>
</template>

<script setup>
const route = useRoute();

useHead({
  title: ` Cars in ${route.params.city}`,
});
</script>

<style lang="scss" scoped></style>
