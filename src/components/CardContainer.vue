<template>
  <main id="CardContainer">
    <div v-for="syn in synArray">
      <Card
        :syn="syn" 
        :generateUrl="generateUrl"
        />
    </div>
  </main>
</template>

<script>
import Card from './Card.vue'

export default {
  name: 'CardContainer',
  components: {
    Card
  },
  props: {
    generateUrl: {type: Function},
    synArray: [],
    syn: ''
  },
  data() {
    return {

    }
  }
}
</script>

<style scoped>
  #CardContainer {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    overflow: scroll;
    height: 82vh;
  }
</style>