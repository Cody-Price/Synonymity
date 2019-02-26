<template>
  <div id="Search">
    <form @submit="$emit(generateUrl(input))" v-on:submit.prevent="onSubmit">
      <input type="text" v-model="input" placeholder="Let's get some synonyms going!"/>
      <button>Search</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'Search',
  props: ["generateUrl"],
  data() {
    return {
      input: ''
    }
  }
}
</script>

<style scoped>
  #Search {
    width: 100vw;
    border-bottom: 3px solid white;
    padding: 0 0 15px 0;
    background-color: rgba(0, 0, 0, 0.61);
  }

  input {
    margin: 0 25px;
    width: 25vw;
    padding: 5px;
    border: rgb(83, 9, 9) 5px solid;
    border-radius: 10px;
    font-size: 1.15rem;
    transition-duration: 0.2s;
  }

  input:focus {
    outline: none;
    transform: scale(1.1);
    transition-duration: 0.2s;
  }

  button {
    padding: 4px 10px;
    font-size: 1.15rem;
    border-radius: 10px;
    border: rgb(83, 9, 9) 5px solid;
  }

  button:focus {
    outline: none;
  }

  button:active {
    background-color: black;
    color: white;
  }
</style>