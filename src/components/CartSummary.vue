<template>
    <div class="cart-summary">
        <p>Cart is empty</p>
    </div>
</template>
 <script >
 export default{
    name: "CartSummary",
    itemCount: {
        type: Number,
        default: 0,
    }
 }
  </script>
