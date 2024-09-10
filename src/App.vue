<template>
  <div id="app">
    <PokemonView />
  </div>
</template>

<script>
import PokemonView from './components/PokemonView.vue';

export default {
  name: 'App',
  components: {
    PokemonView,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #fff;
  margin-top: 20px;
  background: #F64B3C;
}
</style>
