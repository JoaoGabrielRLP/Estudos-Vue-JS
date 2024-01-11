<template>
  <div>
   <h1 :class="{ 'title': true, 'title-home': isHome }"> <!-- chamando a variável no class -->
        Teste em Vue 3
    </h1>  

    <p :class="pClass">
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Excepturi officia unde iusto aspernatur doloribus quidem ut quasi laboriosam molestias inventore!
    </p>

    <p :style="styleClass">
        lipsum dolor sit, amet consectetur adipisicing
    </p>

      <div
          v-for="(obj, index) in todos"
          :key="obj.id"
          class="todos-item"
      >

      <img 
        v-if="obj.imgSrc"
        :src="obj.imgSrc"  
         
      >
      <!-- Podemos usar o v-bind escrevendo apenas os 2 pontos ( : ) -->.
     
          {{ index}} - {{ obj.title }}
      </div>

     

  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
      return {
          isHome: true,
          classVar: 'title',   /**Criando a classe no data */ 
          pClass: ['text', 'text-home'],   
          styleClass: { 'color': 'aqua', backgroundColor: 'black'},   /*Podemos usar notações próprias do Vue para chamar elementos css*/
          imgAlt: 'Foto',          
          todos: [
              {
                  "userId": 1,
                  "id": 1,
                  "title": "delectus aut autem",
                  "completed": false,
                  "imgSrc": 'https://placehold.co/150',
              },
              {
                  "userId": 1,
                  "id": 2,
                  "title": "quis ut nam facilis et officia qui",
                  "completed": false,
                  "imgSrc": 'https://placehold.co/150',
              },
              {
                  "userId": 1,
                  "id": 3,
                  "title": "fugiat veniam minus",
                  "completed": false
              },
              {
                  "userId": 1,
                  "id": 4,
                  "title": "et porro tempora",
                  "completed": true
              },
              {
                  "userId": 1,
                  "id": 5,
                  "title": "laboriosam mollitia et enim quasi adipisci quia provident illum",
                  "completed": false
              }
          ]
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