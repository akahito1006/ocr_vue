<script>
export default {
  name: 'NavLink',
  props: ['url', 'text']
  // here
}
</script>

<template>
  <a :href="url">{{ text }}</a>
</template>

<style>
  a {
    text-decoration-style: double;
  }
</style>