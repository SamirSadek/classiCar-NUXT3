<template>
  <div>
    <div class="font-mono max-w-7xl mx-auto">
      <!-- Hero -->
      <div class="mt-10 border-b-4">
        <img
          class="w-full h-[60vh] rounded"
          src="https://stimg.cardekho.com/images/carexteriorimages/930x620/BMW/XM/10570/1689672872537/front-left-side-47.jpg"
          alt=""
        />
        <h1 class="mt-10 text-4xl">BMW XM</h1>
        <div class="flex justify-between items-center">
          <div class="flex justify-between items-center">
            <p>5 Seats</p>
            <p>|</p>
            <p>67000 miles</p>
          </div>

          <div>
            <p class="font-bold text-2xl">$35000</p>
          </div>
        </div>
      </div>

      <!-- Hero -->
      <div class="mr-10 mt-5 border-b">
        <div class="flex text-lg mt-2">
          <p class="rounded mr-3 text-green-800">✔️</p>
          <p>Leather Interior</p>
        </div>
      </div>
      <!-- description -->
      <div>
        <p class="mb-5 mt-5">
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Reprehenderit dolores
          facere iure laudantium quibusdam, voluptatem odio sit esse molestiae alias?
        </p>
      </div>
      <!-- Contact -->
      <div class="mt-10 mb-10">
        <div class="flex justify-between gap-2">
          <input type="text" class="border p-1 w-1/3" placeholder="Name" />
          <input type="text" class="border p-1 w-1/3" placeholder="Email" />
          <input type="text" class="border p-1 w-1/3" placeholder="Phone" />
        </div>
        <div class="flex justify-between mt-4">
          <textarea
            name=""
            class="border p-1 w-full"
            placeholder="Your Message ..."
          ></textarea>
        </div>
        <div class="text-center">
          <button class="bg-[#000812] text-white px-10 py-3 rounded mt-4">Submit</button>
        </div>
      </div>

      <div></div>
    </div>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped></style>
