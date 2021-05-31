<script>
import HomeLink from "./components/HomeLink.vue"

export default {
  name: 'App',
  components: {
    HomeLink
  }
}
</script>

<template>
  <div id="app">
    <nav>
      <HomeLink />
      <a href="/about">About</a>
      <a href="/contact">Contact</a>
    </nav>
    <p>Welcome to our <HomeLink /> page!</p>
  </div>
</template>