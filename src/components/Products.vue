<template>
<div clas = "product">
  <h2>{{name}}</h2>
  <p v-if ="showPrices">Price: ${{ price }}</p>
    <ul>
    <li 
    v-for="product in products" 
    :key="product"
    :name ="product.name"
    :price ="product.price">
      <span :class="{ 'line-through  ': product.name }">
        {{ product.name }}
      </span>
    </li>
</ul>
      </div>

</template>

<script setup>
import { ref, computed } from "vue";
import {fromCurrency} from "../helpers.js";

export default {
  name: "Products",
  props: {
    name: {
      type: String,
      required: true
    },
    price:{
      type:Number,
      required:true
    },
    showPrices:{
      type: Boolean,
      required: true
    },

  }
}

const products =ref([
    { name: "Samsung", price: 15000 },
    { name: "Readme", price: 10000},
    { name: "Realme", price: 12000},

])
const totalcost = computed(() => products.value.filter((t) => p.TotalPrice).length)
</script>

<style setup>
.expensive{
    color: red; font-weight: bold;
}
.affordable{
    color: green;
}
</style>