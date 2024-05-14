<script setup>
  import Cabecalho from './components/Cabecalho.vue';
  import Formulario from './components/Formulario.vue';
</script>
<template>
  <div class="container">
    <Cabecalho/>
    <Formulario/>
  </div>
</template>

<style scoped>

  input {
    width: 100%;
    height: 100%;
  }
  .resultado {
    margin: 0 auto;
    justify-content: center;
    display: flex;
    height: 100%;
  }
</style>