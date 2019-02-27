<template>
  <header id="Header">
    <h1>Synonymity</h1>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    msg: String
  }
}
</script>

<style scoped>
#Header {
  padding: 1px;
  background-color: rgba(0, 0, 0, 0.61);
}

h1 {
  color: white;
  font-size: 3.5rem;
}
</style>
