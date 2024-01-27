<template>
  <TheHeader>
    <template v-slot:description>
        <p>Description</p>
    </template>

    Conteudo do menu <!-- Quando criamos algo dentro do template e não especificamos o slot, ele pegará o slot sem nome (default) -->
  </TheHeader>    
</template>

<script>
import TheHeader from './components/TheHeader.vue';

export default {
    name: 'App',
    components: { TheHeader },
    data() {
        return {
            name: 'João Gabriel',
            showHeader: true,
        };
    },
    beforeUpdate(){},

    update() {},

    beforeCreate() {},

    created() {},

    beforeMount() {},

    mounted() {}, 
    
    watch: {},
    computed: {},
    methods: {},
}
</script>

<style>
.title{
    font-size: 20px;
    color: blue;
}

.title-home{
    font-size: 40px;
    color: green;
}

.text-home{
    color: #42b983;
}

.text{
    color: rgb(32, 196, 6);
}

.todos-item {
  background: #000;
  margin: 0 0 5px 0;
  padding: 3px 6px;
  color: #fff
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 60px;
}
</style>