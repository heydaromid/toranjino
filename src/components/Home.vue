<template>
    <Header :item="brandItems[0]"/>
    <div v-if="cardsLoading" class="flex-1 my-20">
      <div class="w-10 h-10 border-4 border-green-600 border-t-transparent border-solid rounded-full animate-spin mx-auto"></div>
    </div>
    <main v-else class="flex-1 mx-2 sm:mx-0">
      <div class="flex-1 mb-16">
        <section class="container mx-auto">
          <div class="grid sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-5 gap-4 my-6">
              <ProductCard v-for="item in cardItems" :key="item.index" :cardItem="item.values" :phoneNumber="brandItems[0]"></ProductCard>
          </div>
        </section>
      </div>
    </main>
    <Footer :item="brandItems[0]"/>
</template>

<script setup>
import ProductCard from "../components/ProductCrad.vue";
import Header from "./Header.vue";
import Footer from "../components/Footer.vue";
import { ref } from "vue";

const docId = "_-Dnd-FkLb";
const brandTableId = "grid-5s_DTzk4lU";
const cardsTableId = "grid-OxkfyQYjSp";
const token = "1aa6c074-6bd5-4e6d-9d94-05266516b8a9";
const brandUrl = `https://coda.io/apis/v1/docs/${docId}/tables/${brandTableId}/rows`;
const cardsUrl = `https://coda.io/apis/v1/docs/${docId}/tables/${cardsTableId}/rows`;
const cardsLoading = ref(true);
const brandItems = ref([]);
const cardItems = ref([]);

function getData(url, res, loading = ref(null)){
  fetch(url, {
    method: 'GET',
      headers: {
        'Content-Type': 'application/json',
        'Authorization': `Bearer ${token}`,
      },
    })
    .then(response => response.json())
    .then(data => {
      res.value = data.items;
      loading.value = false;
      })
    .catch((error) => {
        console.error('Error: ', error);
    });
}

getData(brandUrl, brandItems);
getData(cardsUrl, cardItems, cardsLoading);
</script>

<style>
</style>