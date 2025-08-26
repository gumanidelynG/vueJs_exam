<!-- we need to download node and vite and a vue extension-->
<template>
  <div id="app">
    <Products/>
    <CartSummary :itemCount="5" />
  </div>
</template>

<script setup>
import CartSummary from './components/CartSummary.vue'
import Products from './components/Products.vue';
</script>
