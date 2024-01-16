<template>
  <div class="w-full">
    <div
    class=" shadow border w-full overflow-hidden mb-5 cursor-pointer h-[200px] bg-[#000812] rounded font-mono text-white"
  >
    <!-- <img
      class="absolute w-7 right-5 top-2 z-index bg-white p-1 rounded-full border-2 border-red-500"
      :src="favored ? heartFilled : heartOutline"
      alt=""
      @click="emit('favor', car.id)"
    /> -->
    <div class="flex h-full" @click="navigateTo(`/car/${car.name}-${car.id}`)">
      <NuxtImg class="p-4 rounded-3xl w-full" :src="car.url" alt="" />
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
  </div>
</template>

<script setup>
import heartFilled from "../assets/heartFilled.png";
import heartOutline from "../assets/heartOutline.png";
const props = defineProps({
  car: Object,
  favored: Boolean,
});

// const favored = useState(`favored-${props.car.id}`, () => {
//   return false;
// });

const emit = defineEmits(["favor"]);
</script>

<style lang="scss" scoped></style>
