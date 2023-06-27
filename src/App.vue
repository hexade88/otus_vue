<template>
  <div class="AppVue">
    <div class="vheader">
      <div>
        <p>Название</p>
        <input type="text" placeholder="Поиск">
      </div>
      <div>
        <p>Цена</p>
        <input type="text" placeholder="от" style="width: 30px;">
        <input type="text" placeholder="до" style="width: 30px;">
      </div>
    </div>
    <div class="vbody">
      <MyProduct v-for="card in cards" :key="card.id" :card="card" />
    </div>
    
  </div>
 </template>

<script setup>
import { onBeforeMount, onMounted, ref } from 'vue';
import MyProduct from './components/product/MyProduct.vue';
import axios from 'axios';
import ModalForm from './components/ModalForm.vue';

  const cards = ref([])
  const getCard = async () => {
    cards.value = await axios.get('https://fakestoreapi.com/products').then(function(response){
      return response.data;
      });
  }
  
  onMounted(() => {
    window.addEventListener("resize", bodyHeight);
    bodyHeight();
  });
  
  onBeforeMount(getCard);
  
  const bodyHeight = () => {
    document.querySelector(".vbody").style.height = (window.innerHeight - 70) + "px";
  }

</script>

<style scoped>
.vheader{
  width: 100%;
  height: 50px;
  background-color: antiquewhite;
  position: fixed;
}
p{
  margin: 0px;
}
.vheader div{
  float: left;
  margin: 3px 15px 3px 15px;
}
.vbody{
  overflow: auto;
  padding-top: 50px;
}
</style>
