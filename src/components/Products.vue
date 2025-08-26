<template>
  <div v-if="products.length === 0" class="no-products">No available products.</div>
  <div v-else class="products-container">
    <ul class="products-list">
      <li
        v-for="product in products"
        :key="product.name"
        :class="['product-item', product.price >= 1000 ? 'expensive' : 'affordable']"
      >
        <div class="product-details">
          <span class="product-name">{{ product.name }}</span>
          <span v-if="showPrices" class="product-price">{{ formatCurrency(product.price) }}</span>
        </div>
      </li>
    </ul>
    <div v-if="showPrices" class="total-price">
      <strong>Total Price: {{ formatCurrency(totalPrice) }}</strong>
    </div>
  </div>
</template>
<script setup>
import { computed } from 'vue'
import { formatCurrency } from '../helpers.js'

const showPrices = true

const products = [
  { name: 'T-shirt', price: 19.99 },
  { name: 'Jeans', price: 49.99 },
  { name: 'Jacket', price: 89.99 },
  { name: 'Luxury Coat', price: 1200 },
  { name: 'Designer Dress', price: 1500 },
]

const totalPrice = computed(() =>
  products.reduce((sum, product) => sum + product.price, 0)
)
</script>

<style scoped>
.products-container {
  background: #fff;
  border-radius: 12px;
  box-shadow: 0 2px 12px rgba(0,0,0,0.07);
  padding: 24px;
  margin-top: 16px;
}

.products-list {
  list-style: none;
  padding: 0;
  margin: 0 0 16px 0;
}

.product-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 14px 18px;
  margin-bottom: 10px;
  border-radius: 8px;
  background: #f4f7fa;
  transition: box-shadow 0.2s;
  box-shadow: 0 1px 4px rgba(0,0,0,0.03);
}

.product-item.expensive {
  border-left: 6px solid #e74c3c;
  color: #e74c3c;
  font-weight: bold;
}

.product-item.affordable {
  border-left: 6px solid #27ae60;
  color: #27ae60;
}

.product-details {
  display: flex;
  flex-direction: column;
}

.product-name {
  font-size: 1.1rem;
  font-weight: 500;
}

.product-price {
  font-size: 1rem;
  margin-top: 4px;
  opacity: 0.85;
}

.total-price {
  text-align: right;
  font-size: 1.15rem;
  color: #4f8a8b;
  margin-top: 8px;
  font-weight: bold;
}

.no-products {
  text-align: center;
  color: #888;
  font-size: 1.1rem;
  padding: 32px 0;
}
</style>
