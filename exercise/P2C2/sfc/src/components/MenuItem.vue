<script>
export default {
  name: 'MenuItem',
  props: ['addToShoppingCart', 'quantity', 'inStock', 'name', 'image']
  //   <MenuItem 
  //   v-for="item in simpleMenu"
  //   :key="item.name" 
  //   :addToShoppingCart="addToShoppingCart"
  //   :quantity="item.quantity"
  //   :inStock="item.inStock"
  //   :name="item.name"
  //   :image="item.image"
  // />
}
</script>

<template>
  <div class="menu-item">
    <img
      class="menu-item__image"
      :src="image.source"
      :alt="image.alt"
    />
    <!-- :image="item.image"より、itemを消す 以下同様-->
    <div>
      <h3>{{ name }}</h3>
      <p v-if="inStock">In Stock</p>
      <p v-else>Out of Stock</p>
      <div>
        <label for="add-item-quantity">
          Quantity: {{ quantity }}
        </label>
        <input 
          v-model.number="quantity" 
          id="add-item-quantity" 
          type="number" 
        />
        <!-- コンポーネントでv-modelを使う https://jp.vuejs.org/v2/guide/components.html#%E3%82%B3%E3%83%B3%E3%83%9D%E3%83%BC%E3%83%8D%E3%83%B3%E3%83%88%E3%81%A7-v-model-%E3%82%92%E4%BD%BF%E3%81%86 -->
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