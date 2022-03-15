<template>
    <div class="border rounded-lg p-4 flex flex-col justify-between gap-4 card">
      <div class="flex sm:flex-col sm:justify-around gap-3">
        <div class="w-1/3 sm:w-auto">
          <img :src="cardItem['c-WoMta3EdKU']" alt="تصویر محصول" class="block mx-auto sm:h-52">
        </div>
        <div class="flex flex-col justify-between w-2/3 sm:w-auto gap-3">
          <h3 class="font-semibold text-lg text-gray-700 card-title">{{ cardItem['c-zNhlqGccUo'] }}</h3>
          <p class="font-light text-gray-600 line-clamp-2">{{ cardItem['c-ehIiJHuNqx'] }}</p>
          <div class="flex justify-between sm:hidden">
            <a :href="`tel:${phoneNumber.values['c-84H1Sygs7g']}`" class="bg-green-500 hover:bg-green-600 text-white rounded-full py-1 px-4">سفارش</a>
            <div class="flex items-center gap-1">
                <span>{{ cardItem['c-GMAP2hhQnB'] }}</span>
                <img src="../assets/Images/Toman.svg" width="18">
            </div>
          </div>
        </div>
      </div>
      <div class="justify-between hidden sm:flex">
          <a :href="`tel:${phoneNumber.values['c-84H1Sygs7g']}`" class="bg-green-500 hover:bg-green-600 text-white rounded-full py-1 px-4">سفارش</a>
          <div class="flex items-center gap-1">
              <span>{{ cardItem['c-GMAP2hhQnB'] }}</span>
              <img src="../assets/Images/Toman.svg" width="18">
          </div>
      </div>
    </div>
</template>

<script setup>
defineProps({
  cardItem: Object,
  phoneNumber: Object,
})
</script>

<style>

</style>