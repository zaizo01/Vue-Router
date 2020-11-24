<template>
  <titulo text="Ruta con Parametros"/>
    <h2>Parametro: {{ $route.params.id }}</h2>
    <h3>{{ articulo.title }}</h3>
    <p>{{ articulo.body }}</p>
</template>

<script>
import Titulo from '../components/Titulo.vue'
export default {
    components: {
        Titulo
    },
    data() {
        return {
            articulo: {}
        }
    },
    methods: {
        async consumirArticulo(){
            try {
                const data = await fetch(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`);
                const obj = await data.json();
                this.articulo = obj;
            } catch (error) {
                console.log(error);
            }
        }
    },
    created() {
      this.consumirArticulo();
    },
}
</script>

<style>

</style>