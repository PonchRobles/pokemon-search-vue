<template>
  <div id="app">
    <!-- <img alt="Pokemon Logo" src="./assets/pokemon_logo.gif"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
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

<style lang="scss">
  @import url('https://use.fontawesome.com/releases/v5.8.2/css/all.css');
  body {
    margin: 0;
    padding: 0;
  }
</style>