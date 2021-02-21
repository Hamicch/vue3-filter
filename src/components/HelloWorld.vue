<template>
  <div>
     <h2>Vue 3 Filter</h2>
     <input 
      type='text' 
      placeholder='Filter Search' 
      v-model='query'
    />
 <div class="btn"><button @click='reset'> Reset </button></div>
  <SearchResults :query='query' />
   </div>
</template>

<script>

import { ref } from 'vue'
import  SearchResults  from './SearchResults.vue'

  export default {
    components: {
      SearchResults
    },

    setup () {
      
      const query = ref('')

      const reset = (evt) => {
        query.value = '' // clears the query
      }

      return {
        reset,
       query
      }
    }
  }
</script>

<style lang="scss" >
button {
  margin: 30px;
  height: 2.5em;
  width: 5em;
  background: #35495e;
  color: white;
  border: none;
  border-radius: 0.5em;
  outline: none;

    &:hover {
    outline: none;
    outline-color: none;
    background-color: #41b883;
    cursor: pointer;
    }
}
input[type="text"] {
  height: 2.5em;
  width: 15em;
  border-radius: 0.5em;
  outline: none;
  background-color: #f0fcf7;
  border: none;
  font-style: italic;
  padding: 2px 20px 2px 20px;

  &:focus {
    outline-color: #41b883;
  }
}
</style>