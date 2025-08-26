<!-- we need to download node and vite and a vue extension-->
<template>
  <div>
   <h1>User Profiles</h1>
    <div style="display: flex; flex-wrap: wrap;">
      <Products
        v-for="(product, index) in Products"
        :key="index"
        :name="product.name"
        :price="product.price"
        
      />
    <Products />
    <CartSummary />
  </div>
</template>
<script setup>
import Products from './components/Products.vue'
import CartSummary from './components/CartSummary.vue'

</script>