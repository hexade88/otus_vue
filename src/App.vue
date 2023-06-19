<script setup>
//import { RouterLink, RouterView } from 'vue-router'
//import HelloWorld from './components/HelloWorld.vue'
import { ref } from 'vue';
import MyProduct from './components/product/MyProduct.vue';
import axios from 'axios';

</script>

<template>
  <div>
    <MyProduct />
    <div></div>
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
