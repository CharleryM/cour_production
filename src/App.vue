<template>
  <div>
    <Formulaire />
    <BarGraph />
  </div>
</template>

<script>
import BarGraph from './components/BarGraph.vue';
import Formulaire from './components/Form.vue'

export default {
  name: 'App',
  components: {
    BarGraph,
    Formulaire
  }
}
</script>

<style scoped>
h1 {
  color: #2c3e50;
}
</style>

