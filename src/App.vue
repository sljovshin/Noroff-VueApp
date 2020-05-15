<template>
  <div id="app">
    <Data />
  </div>
</template>

<script>
import Data from './components/Data';


export default {
  name: 'App',
  components: {
    Data
  },
  data() {
    return {
      
    }
  },
  created() {

  },

  methods: {
    
    
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
</style>


/*
'https://jsonplaceholder.typicode.com/todos?_limit=5'
*/