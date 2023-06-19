<script setup>
//import { RouterLink, RouterView } from 'vue-router'
//import HelloWorld from './components/HelloWorld.vue'
import { onBeforeMount, ref } from 'vue';
import MyProduct from './components/product/MyProduct.vue';
import axios from 'axios';

  const cards = ref([])
  const getCard = async () => {
    cards.value = await axios.get('https://fakestoreapi.com/products').then(function(response){
      return response.data;
      });
  }
  onBeforeMount(getCard);

</script>

<template>
  <div>
    <MyProduct v-for="card in cards" :key="card.id" :card="card" />
  </div>
 <!--<header>
    

    <div class="wrapper">
      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />-->
</template>

<style scoped>
</style>
