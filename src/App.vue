<template>
  <div>
    <BaseAlert 
      v-if="showAlert"
      :variant="variant"
      @close="onClose()"
    > 
      {{ text }}
    </BaseAlert> <!-- Aqui dizemos que o prop variant recebe sucess -->
  </div>
</template>

<script>
import BaseAlert from './components/BaseAlert.vue';


export default {
    name: 'App',
    data() {
        return {
          showAlert: true,
          variant: 'success',
          text: 'Seu formulário foi enviado'
        };
    },
    beforeUpdate() { },
    update() { },
    beforeCreate() { },
    created() { },
    beforeMount() { },
    mounted() { },
    watch: {},
    computed: {},
    methods: {
      onClose(){
        this.showAlert = false
        console.log('On close')
      }
    },
    components: { BaseAlert }
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