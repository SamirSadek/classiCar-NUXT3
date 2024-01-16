<template>
  <div class="shadow  border w-80 mr-10 text-white bg-[#000812] rounded font-mono h-64">
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
    <!-- ------------------------ -->
    <div class="p-5 flex justify-between relative cursor-pointer border-b">
      <h3>Made By</h3>
      <h3 class="capitalize font-bold" @click="updateModal('make')">
        {{ route.params.make || "Any" }}
      </h3>
      <div
        v-if="modal.make"
        class="absolute border left-64 shadow p-5 top-1 -m-1 bg-white w-[600px] flex justify-between flex-wrap"
      >
        <h4
          v-for="make in makes"
          :key="make"
          class="w-1/3 text-black"
          @click="onChangeMake(make)"
        >
          {{ make }}
        </h4>
        <button class="bg-[#000812] text-white w-full mt-2 rounded p-1">Apply</button>
      </div>
    </div>
   <!-- -------------------------------- -->
    
    <div class="p-5 flex justify-between relative cursor-pointer border-b">
      <h3>Price</h3>
      <h3 class="capitalize font-bold" @click="updateModal('price')">{{priceRangeText}}</h3>
      <div class="absolute border left-64 shadow p-5 top-1 -m-1 bg-white" v-if="modal.price">
       <input type="number" class="border rounded p-1 text-black" placeholder="Min Price" v-model="priceRange.min">
       <input type="number" class="border rounded p-1 text-black mt-2" placeholder="Max Price" v-model="priceRange.max">
       <button class="bg-[#000812] text-white w-full mt-2 rounded p-1" @click="onPriceChange">Apply</button>
       </div>
    </div>
  </div>
</template>

<script setup>
const { makes } = useCar();
const modal = ref({
  make: false,
  location: false,
  price: false,
});

const priceRange = ref({
  min:'',
  max:''
})

const updateModal = (key) => {
  modal.value[key] = !modal.value[key];
};
const route = useRoute();
 const router = useRouter();

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

const onPriceChange = ()=>{
  updateModal("price");
  if(priceRange.value.max && priceRange.value.min){
    if(priceRange.value.min > priceRange.value.max){
      return
    }
    router.push({
      query:{
        minPrice: priceRange.value.min,
        maxPrice: priceRange.value.max,
      }
    })
  }
}

const priceRangeText = computed(()=>{
  const minPrice = route.query.minPrice;
  const maxPrice = route.query.maxPrice;

  if(!minPrice && !maxPrice) return "Any"
  else if (!minPrice && maxPrice){
    return `< $${maxPrice}`
  }
  else if (minPrice && !maxPrice){
    return `> $${minPrice}`
  }else{
    return `$${minPrice} - $${maxPrice}`
  }
})

const onChangeMake = (make) => {
  updateModal("make");
  navigateTo(`/city/${route.params.city}/car/${make}`);
};
</script>

<style lang="scss" scoped></style>
