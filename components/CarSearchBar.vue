import type { callWithAsyncErrorHandling } from 'vue'; import type { compileStyle } from
'vue/compiler-sfc';
<template>
  <div
    class="font-serif text-2xl rounded-full bg-white flex justify-between overflow-hidden drop-shadow-2xl mx-auto"
  >
    <input
      type="text"
      class="py-3 px-5 w-full text-2xl rounded-full focus:outline-none"
      :class="cityError ? 'border-4 border-red-600' : ''"
      placeholder="Search by City ..."
      v-model="city"
    />
    <button
      @click="handleSearch"
      class="bg-[#000812] text-white px-5 border-2 border-white rounded-full py-3"
    >
      Search
    </button>
  </div>
</template>

<script setup>
const city = ref("");
const cityError = ref(false);
// const router = useRouter();
const handleSearch = () => {
  if (!city.value) {
    return (cityError.value = true);
  }
  // router.push(`/city/${city.value}/car`);
  navigateTo(`/city/${city.value}/car`);
};
</script>

<style lang="scss" scoped></style>
