<template>
  <div
    class="shadow border w-full overflow-hidden mb-5 cursor-pointer h-[200px] bg-[#000812] rounded font-mono text-white"
    @click="navigateTo(`/car/${car.name}-${car.id}`)"
  >
    <div class="flex h-full">
      <img class="p-4 rounded-3xl w-1/3" :src="car.url" alt="" />
      <div class="p-4 flex flex-col">
        <div>
          <h1 class="text-2xl text-blue-500 font-bold">{{ car.name }}</h1>
          <p>
            Latest Update: BMW has launched the XM in India. It is the most powerful M
            road car from BMW so far BMW has priced the XM at Rs 2.6 crore (ex-showroom
            Delhi).It gets its power from a 4.4-litre twin-turbo V8 petrol engine in a
            hybrid system that churns out
          </p>
          <h1 class="text-blue-500">Price: {{ car.price }}$</h1>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  car: Object,
});
</script>

<style lang="scss" scoped></style>
