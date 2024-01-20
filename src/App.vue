<template>
  <div>
    <input 
        v-model="name"
        type="text"
      > <br>

      {{ name }}

      <br><br>

      <input 
        v-model="user.first_name"
        type="text"
      > <br>

      <input 
        v-model="user.last_name"
        type="text"
      > <br>

      {{ user.first_name }} {{ user.last_name }}
      
      <br><br>

      <select v-model="pageCount">
        <option value="5">5</option>
        <option value="10">10</option>
        <option value="15">15</option>
      </select>
      {{ pageCount }}
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
      return {
        name: '',
        pageCount: 5,
        user: {
          first_name: '',
          last_name: ''
        }   
      }
  },

  watch:{
    name(vl){
        if(vl.length >= 3){
          this.saveUserName();
        }        
      },
      pageCount(){
        this.changePage();
      },

      user: {
        handler(){
          console.log('User alterado')
        }, /**O handler significa que, quando o user (vinculado ao objeto por ter o mesmo nome) for alterado, deve executar o que estiver dentro das chaves */

        deep: true /**Quando for alterado algo no objeto em si (definido em data() ) dispare o handler */
      } /**Para observarmos objetos, é necessário declarar dessa maneira */
  },

  computed:{    
  }, 

  methods: {   
    saveUserName(){
      console.log('Ajax');
      console.log(this.name);     
    },

    changePage(){
      console.log('Ajax changePage')
    }
  }
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