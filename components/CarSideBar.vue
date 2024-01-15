<template>
  <div class="shadow border w-80 mr-10 text-white bg-[#000812] rounded font-mono h-64">
    <h2 class="text-center m-2 p-2 text-xl border-b font-bold">Filter Your Car</h2>
    <div class="p-5 flex justify-between relative cursor-pointer border-b">
      <h3>Location</h3>
      <h3 @click="updateModal('location')" class="capitalize font-bold">
        {{ route.params.city }}
      </h3>
      <div
        v-if="modal.location"
        class="absolute border left-64 shadow p-5 top-1 -m-1 bg-white"
      >
        <input type="text" class="border rounded p-1 text-black" v-model="city" />
        <button
          @click="onChangeLocation"
          class="bg-[#000812] text-white w-full mt-2 rounded p-1"
        >
          Apply
        </button>
      </div>
    </div>
    <div class="p-5 flex justify-between relative cursor-pointer border-b">
      <h3>Made By</h3>
      <h3 class="capitalize font-bold">Any</h3>
      <!-- <div class="absolute border left-72 shadow p-5 top-1 -m-1 bg-white">
       <input type="text" class="border rounded p-1">
       <button class="bg-[#000812] text-white w-full mt-2 rounded p-1">Apply</button>
       </div> -->
    </div>
    <div class="p-5 flex justify-between relative cursor-pointer border-b">
      <h3>Price</h3>
      <h3 class="capitalize font-bold">Any</h3>
      <!-- <div class="absolute border left-72 shadow p-5 top-1 -m-1 bg-white">
       <input type="text" class="border rounded p-1">
       <button class="bg-[#000812] text-white w-full mt-2 rounded p-1">Apply</button>
       </div> -->
    </div>
  </div>
</template>

<script setup>
const modal = ref({
  make: false,
  location: false,
  price: false,
});

const updateModal = (key) => {
  modal.value[key] = !modal.value[key];
};
const route = useRoute();

const city = ref("");
const onChangeLocation = () => {
  if (!city.value) return;
  if (!isNaN(parseInt(city.value))) {
    throw createError({
      statusCode: 404,
      message: "Invalid City Format",
    });
  }
  updateModal("location");

  navigateTo(`/city/${city.value}/car/${route.params.make}`);
  city.value = "";
};
</script>

<style lang="scss" scoped></style>
