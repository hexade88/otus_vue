<template>
  <div class="">
    <ModalForm />
    <MyProduct v-for="card in cards" :key="card.id" :card="card" />
  </div>
 </template>



<script setup>
import { onBeforeMount, ref } from 'vue';
import MyProduct from './components/product/MyProduct.vue';
import axios from 'axios';
import ModalForm from './components/ModalForm.vue';

  const cards = ref([])
  const getCard = async () => {
    cards.value = await axios.get('https://fakestoreapi.com/products').then(function(response){
      return response.data;
      });
  }
  onBeforeMount(getCard);

</script>

<style scoped>
</style>
