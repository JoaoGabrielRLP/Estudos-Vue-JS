<template>
  <div>
    <BaseCard />
  </div>
</template>

<script>
import BaseCard from '@/components/BaseCard'; // O @ significa que estamos dentro da pasta SRC
export default {
    name: 'App',
    components: { BaseCard },
    data() {
        return {
            
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