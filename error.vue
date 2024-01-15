<template>
  <div class="flex h-screen justify-center items-center flex-col">
    <h1 class="text-red-600 text-7xl">{{ error.statusCode }}</h1>
    <p class="mt-5 text-4xl">{{ error.message }}</p>
    <button @click="handleError" class="btn rounded mt-5 bg-blue-400 p-2">Go Back</button>
  </div>
</template>

<script setup>
const error = useError();
const handleError = () => {
  navigateTo("/");
};
</script>

<style lang="scss" scoped></style>
