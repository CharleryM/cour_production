<template>
  <div>
    <Formulaire />
    <Graph />
  </div>
</template>

<script>
import Graph from './components/Graph.vue';
import Formulaire from './components/Form.vue'

export default {
  name: 'App',
  components: {
    Graph,
    Formulaire
  }
}
</script>

<style scoped>
h1 {
  color: #2c3e50;
}
</style>
