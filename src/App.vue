<template>
  <div id="app">
    <Header />
    <Search 
      :generateUrl="generateUrl"
      />
    <CardContainer 
      :synArray="synArray"
      :generateUrl="generateUrl"
      />
  </div>
</template>

<script>

import Header from './components/Header.vue'
import Search from './components/Search.vue'
import CardContainer from './components/CardContainer.vue'
import apiKey from '../utilities/apiKey.js'

export default {
  name: 'app',
  components: {
    Header,
    Search,
    CardContainer
  },
  data() {
    return {
      synArray: []
    }
  },
  methods: {
    generateUrl: async function(word) {
      let url = "https://dictionaryapi.com/api/v3/references/thesaurus/json/" + word.toLowerCase() + "?key=" + apiKey
      try {
        let response = await fetch(url)
        let result = await response.json()
        let synonyms = result[0].meta.syns
        let cleanResults = synonyms.reduce((acc, currVal) => {
          currVal.forEach(synonym => {
            acc.push(synonym)
          })
          return acc
        }, [])
        this.$data.synArray = cleanResults
      } catch(err) {
        this.$data.synArray = err
      }
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Crete+Round');

* {
  font-family: 'Crete Round', Arial, Helvetica, sans-serif;
}

html {
  margin: 0;
  padding: 0;
}

body {
  margin: 0;
  height: 96vh;
}

#app {
  background-image: url("../library-desk.jpg");
  background-size: cover;
  min-height: 103vh;
  width: 100vw;
  position: relative;
  top: -25px;
  text-align: center;
  margin: none;
  padding: none;
}
</style>
