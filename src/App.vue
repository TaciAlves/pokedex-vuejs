<template>
  <div id="app">
    <Pokemon />
  </div>
</template>


<script>
  import Pokemon from './components/Pokemon.vue'

  export default {
    components: {
      Pokemon
    }
  }
</script>


<style lang='scss'>
  @import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.2.0/css/all.min.css');
  
  body {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
</style>
