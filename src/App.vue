<template>
  <h1> Pré-Test, Lili.ai</h1>  
  <Compteur/>
</template>

<script>
import Compteur from './components/Compteur.vue'

export default {
  name: 'App',
  components: {
    Compteur,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
