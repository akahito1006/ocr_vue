<template>
  <div id="app" class="app">
    <h1>{{ restaurantName }}</h1>
    <p class="description">
      Welcome to {{ restaurantName }}! We are known for our freshly baked
      bread and french pastries! Give you morning a warm start or treat
      yourself in the middle of the day. Our butter is imported from local
      farmers in France. Once you take your first bite, you will see why
      everyone can't get enough!
    </p>

    <section class="menu">
      <h2>Menu</h2>
      <MenuItem 
        v-for="item in simpleMenu"
        :key="item.name" 
        :addToShoppingCart="addToShoppingCart"
        :quantity="item.quantity"
        :inStock="item.inStock"
        :name="item.name"
        :image="item.image"
      />
    </section>

    <aside class="shopping-cart">
      <h2>Shopping Cart: {{ shoppingCart }} items</h2>
    </aside>

    <h2>Contact Us</h2>
    <p>Address: {{ address }}</p>
    <p>Phone: {{ phone }}</p>
    <p>Email: {{ email }}</p>
    <p>Hours:</p>
    <ul>
      <li>M-F: 06:00 to 16:00</li>
      <li>Saturday: 07:00 to 14:00</li>
      <li>Sunday: 07:00 to 12:00</li>
    </ul>
    <footer class="footer">
      <p>{{ copyright }}</p>
    </footer>
  </div>
</template>

<script>
import MenuItem from './components/MenuItem.vue'

export default {
  name: 'App',
  components: {
    MenuItem
  },
  // data プロパティはreturnで内容を返す関数として記述する
  data() {
    return {
      address: '9274 Beurre Ave, Paris, France',
      email: 'hello@cafewithavue.bakery',
      phone: '+08 88 88 88 88 88',
      restaurantName: 'Cafe with A Vue',
      shoppingCart: 0,
      simpleMenu: [
        {
          name: 'Crossiant',
          image: {
            source: '/images/crossiant.jpg',
            alt: 'A crossiant'
          },
          inStock: true,
          quantity: 1
        },
        {
          name: 'French Baguette',
          image: {
            source: '/images/french-baguette.jpeg',
            alt: 'Four French Baguettes'
          },
          inStock: true,
          quantity: 1
        },
        {
          name: 'Éclair',
          image: {
            source: '/images/eclair.jpg',
            alt: 'Chocolate Éclair'
          },
          inStock: false,
          quantity: 1
        }
      ]
    }
  },
  computed: {
    copyright() {
      const currentYear = new Date().getFullYear()

      return `Copyright ${this.restaurantName} ${currentYear}`
    }
  },
  methods: {
    addToShoppingCart(amount) {
      this.shoppingCart += amount
    }
  }
}
</script>

<style lang="scss">
.app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.description {
  max-width: 960px;
  font-size: 1.2rem;
  margin: 0 auto;
}

.footer {
  text-align: center;
  font-style: italic;
}

.menu {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.menu-item {
  display: flex;
  width: 500px;
  justify-content: space-between;
  margin-bottom: 30px;
}

.menu-item__image {
  max-width: 300px;
}
.shopping-cart {
  position: absolute;
  right: 30px;
  top: 0;
}
</style>
