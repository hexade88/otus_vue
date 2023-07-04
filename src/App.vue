<template>
  <div class="AppVue">
    <div class="vheader">
      <div>
        <p>Название</p>
        <input type="text" placeholder="Поиск" v-model="productName">
      </div>
      <div>
        <p>Цена</p>
        <input type="text" placeholder="от" style="width: 30px;" v-model.number="costA">
        <input type="text" placeholder="до" style="width: 30px;" v-model.number="costB">
      </div>
      <div>
        <p>Корзина {{ korzina.length }}</p>
      </div>
    </div>
    <div class="vbody">
      <MyProduct v-for="card in cardsFilt" :key="card.id" :card="card" @mychange="onMyChange" />
    </div>
    
  </div>
 </template>

<script setup>
import { computed, onBeforeMount, onMounted, ref } from 'vue';
import MyProduct from './components/product/MyProduct.vue';
import axios from 'axios';
import ModalForm from './components/ModalForm.vue';

  const cards = ref([])
  const productName = ref('')
  const costA = ref(0)
  const costB = ref(0)
  const getCard = async () => {
    cards.value = await axios.get('https://fakestoreapi.com/products').then(function(response){
      return response.data;
      });
  }

  const korzina = ref([])

  const onMyChange = (args) => {
    const {id, checked} = args;
    if(checked){
      if(korzina.value.indexOf(id)){korzina.value.push(id);}
    } else {
      korzina.value = korzina.value.filter(f => f != id);
    }
  };

  const cardsFilt = computed(() => {
    let product = cards.value;
    if(productName.value != '' || costA.value != 0 | costB.value != 0){
      product = product.filter((prod) => {
        return prod.title.toUpperCase().indexOf(productName.value.toUpperCase()) !== -1 
        });
    }
    if(costA.value != 0){
      product = product.filter((prod) => {
        return prod.price >= costA.value;
      });
    }
    if(costB.value != 0){
      product = product.filter((prod) => {
        return prod.price <= costB.value;
      });
    }
    return product;
  });
  
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
