<template>
  <div class="grid-container-6">
    <div class="colomne-grid" v-for="n in 24" :key="n">
      <p>{{ contenu }}</p>
     </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      contenu: 'image du reçu' // Initialisation de contenu
    };
  }
}
</script>

<style scoped>
.grid-container-6 {
  display: grid;
  grid-template-columns: auto auto auto auto auto auto;
  padding: 10px;
} 

.colomne-grid{
  text-align: center;
}
</style>
