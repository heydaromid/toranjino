<template>
    <header class="container mx-auto">
        <div class="mt-6 flex flex-col gap-3">
            <img class="mx-auto" :src="item.values['c-l7DcP3ny0V']" width="150">
            <h1 class="text-center text-2xl font-semibold cursor-default text-gray-700 mb-4" >لیست محصولات فروشگاه {{ item.name }}</h1>
            <input @keyup="check" v-model.trim="search" type="text" class="outline-none px-3 py-2 mx-2 sm:mx-0 border rounded-lg focus:ring-green-200 focus:ring-2 focus:border-green-500"
            placeholder="نام محصول مورد نظرتان را وارد کنید ...">
        </div>
    </header>
</template>

<script setup>
import { ref } from "vue";

defineProps({
  item: Object,
})

const search = ref();

function check() {
    const card = document.querySelectorAll('.card');
    for (let i = 0; i < card.length; i++) {
        const cardTitle = card[i].querySelector('.card-title');
        const txtValue = cardTitle.textContent || cardTitle.innerText;
        if (txtValue.indexOf(search.value) > -1) {
            card[i].classList.remove('hidden');
        } else {
            card[i].classList.add('hidden');
        }
    }
}
</script>

<style>

</style>