<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <titulo text="Pagina de Inicio"/>
  </div>
</template>

<script>

import Titulo from '../components/Titulo.vue'
export default {
  name: 'Home',
  components: {
    Titulo
  }
}
</script>
