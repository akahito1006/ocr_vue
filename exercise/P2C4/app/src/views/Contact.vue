<template>
<div>
  <p>Address: {{ address }}</p>
  <p>Phone: {{ phone }}</p>
  <p>Email: {{ email }}</p>
</div>
</template>

<script>
export default {
  name: 'Contact',
  props: ['address', 'phone', 'email']
}
</script>

<style></style>