<template>
  <div>
    <h1>Teste</h1>
    <TheHeader v-if="showHeader" />
    <br>
    <input 
        v-model="name"
        type="text"
    >
    {{ name }} <br>
    <button @click="showHeader = !showHeader"> <!-- Lógica simples para realizar apenas um alteração de variável -->
      Toggle
    </button>
  </div>
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
    /*beforeUpdate(){
        console.log('before update', this.name)
    },

    update(){
        console.log('updated', this.name)
    },
     beforeCreate() { 
        console.log('Before create'); //* Não tem acesso ao estado nem ao dom
        console.log('Estado: ', this.name);
        console.log('Dom: ', this.$el);
        /**El seria como se fosse o root, pois vai puxar o elemento raiz do componente na template
    },
    created() {
        console.log('Created');
        console.log('Estado: ', this.name); //* Tem acesso ao estado mas nao ao dom
        console.log('Dom: ', this.$el);
    },
    beforeMount() {
        console.log('Before amount');
        console.log('Estado: ', this.name); //* Tem acesso ao estado mas nao ao dom
        console.log('Dom: ', this.$el);
    },
    mounted() {
        console.log('mounted');
        console.log('Estado: ', this.name); //* Tem acesso ao estado e ao dom
        console.log('Dom: ', this.$el);
    }, */
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