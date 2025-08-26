<script setup>
defineProps({
  itemCount: {
    type: Number,
    required: true,
  },
})
</script>

<template>
  <div class="cart-summary">
    <span class="cart-icon">🛒</span>
    <span class="cart-text">Items in cart:</span>
    <span class="cart-count">{{ itemCount }}</span>
  </div>
</template>

<style scoped>
.cart-summary {
  display: flex;
  align-items: center;
  background: #f4f7fa;
  border-radius: 8px;
  padding: 10px 18px;
  box-shadow: 0 1px 4px rgba(0,0,0,0.03);
  font-size: 1.1rem;
  font-weight: 500;
  color: #4f8a8b;
  margin-bottom: 8px;
}

.cart-icon {
  font-size: 1.5rem;
  margin-right: 10px;
}

.cart-text {
  margin-right: 6px;
}

.cart-count {
  background: #27ae60;
  color: #fff;
  border-radius: 6px;
  padding: 2px 10px;
  font-weight: bold;
  margin-left: 4px;
}
</style>
