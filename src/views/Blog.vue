<template>
  <titulo text="Titulo de mi Blog" />
  <div v-for="arr in arrBlog" :key="arr.id">
    <router-link :to="`/blog/${arr.id}`">
      {{ arr.title }}
    </router-link>
  </div>
</template>

<script>
import Titulo from '../components/Titulo.vue'
export default {
    components: {
        Titulo
    },
    data() {
        return {
            arrBlog: []
        }
    },
    methods: {
        async consumirApi(){
            try {
                const data = await fetch('https://jsonplaceholder.typicode.com/posts');
                const arr = await data.json();
                console.log(arr);
                this.arrBlog = arr;
            } catch (error) {
                console.log(error);
            }
        }
    },
    created() {
      this.consumirApi();
    },
}
</script>

<style>

</style>