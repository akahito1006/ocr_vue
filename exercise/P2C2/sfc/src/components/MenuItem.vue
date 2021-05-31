<script>
export default {
  name: 'MenuItem',
  props: ['addToShoppingCart', 'quantity', 'inStock', 'name', 'image']
}
</script>

<template>
  <div class="menu-item">
    <img
      class="menu-item__image"
      :src="item.image.source"
      :alt="item.image.alt"
    />
    <div>
      <h3>{{ name }}</h3>
      <p v-if="inStock">In Stock</p>
      <p v-else>Out of Stock</p>
      <div>
        <label for="add-item-quantity">
          Quantity: {{ quantity }}
        </label>
        <input
          v-model.number = 'quantity'
          id="add-item-quantity"
          type="number"
        />
        <button @click="addToShoppingCart(quantity)">
          Add to Shopping Cart
        </button>
      </div>
    </div>
  </div>
</template>

<style>
.menu-item {
  display: flex;
  width: 500px;
  justify-content: space-between;
  margin-bottom: 30px;
}

.menu-item__image {
  max-width: 300px;
}
</style>