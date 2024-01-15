<template>
  <div>
    <div class="max-w-7xl mx-auto">
      <div class="mt-16 flex">
        <!-- Side Bar -->
        <NuxtErrorBoundary>
          <CarSideBar />
          <!-- Side Bar -->

          <NuxtPage />
          <template #error="{ error }">
            <div class="text-center mx-auto flex flex-col">
              <h1>Sorry , something went wrong</h1>
              <code>{{ error }}</code>
              <button
                class="text-white bg-black px-10 py-3 rounded mt-4"
                @click="error.value = null"
              >
                go back
              </button>
            </div>
          </template>
        </NuxtErrorBoundary>
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
