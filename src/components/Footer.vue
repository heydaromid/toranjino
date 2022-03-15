<template>
  <footer class="bg-gray-200 h-12 flex items-center">
      <div class="container mx-auto text-center text-black font-light text-sm">
          تمامی حقوق مادی و معنوی برای فروشگاه {{ item.name }} محفوظ می‌باشد. قدرت گرفته از 
          <a href="https://landing24.ir" class="text-green-800 hover:text-green-600 font-bold">لندینگ ۲۴</a>
      </div>
  </footer>
</template>

<script setup>
defineProps({
  item: Object,
})
</script>

<style>

</style>