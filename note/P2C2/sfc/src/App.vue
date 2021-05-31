<script>
import NavLink from "./components/NavLink.vue"

export default {
  name: 'App',
  components: {
    NavLink
  }
}
</script>

<template>
  <div id="app">
    <nav>
      <NavLink url="/" text="Home" />
      <NavLink url="/about" text="About" />
      <NavLink url="/contact" text="Contact" />
    </nav>
  </div>
</template>