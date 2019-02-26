<template>
  <div id="Card" @click="$emit(generateUrl(syn))">
    <p class="synonym">{{ syn }}</p>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: ["syn", "generateUrl"]
}
</script>

<style scoped>
  #Card {
    height: 150px;
    width: 150px;
    border: white 2px solid;
    color: white;
    background-image: url("../../mahogany.jpg");
    background-size: cover;
    margin: 15px;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 15px;
    transition-duration: 0.3s;
    cursor: pointer;
    font-size: 1.5rem;
  }

  #Card:hover {
    transform: scale(1.05);
    transition-duration: 0.3s;
    border: black 5px solid;
  }

  .synonym {
    cursor: pointer;
    word-wrap: break-word;
  }
</style>