<template>
  <div>
    {{ fullName }}

    <h2>Todos em aberto</h2>
  </div>  <br><br>
  
  <div
    v-for="todo in uncompletedTodos" 
    :key="todo.id"
  > <!-- Percorrendo a lista que está em uncompletedTodos -->
    {{ todo.title}} 
  </div>

  <h2>Todos completadas</h2>

  <div
    v-for="todo in completedTodos" 
    :key="todo.id"
  > <!-- Percorrendo a lista que está em completedTodos -->
    {{ todo.title}} 
  </div>

  <br><br><br>

  <h2>Todos </h2>

  <div
    v-for="todo in todos" 
    :key="todo.id"
  > 

    <input 
      v-model="todo.completed"
      type="checkbox"
    >
    {{ todo.title}} 

    <!-- O checkbo permite que seja alterado um valor no array de objetos, obejtos esses que está sendo percorrido por 2 métodos: completedTodos() e uncompletedTodos(), essas funções mostram se o ítem do objeto é verdadeiro ou falso respectivamente e ao alterar essa valor com o checkbo, a lista será recomputada dinamicamente -->
  </div>


</template>

<script>
export default {
  name: 'App',
  data() {
      return {
          user: {
            first_name: 'João',
            last_name: 'Gabriel'
          },

            todos: 

          [
    {
    "userId": 1,
    "id": 1,
    "title": "delectus aut autem",
    "completed": false
    },
  {
    "userId": 1,
    "id": 2,
    "title": "quis ut nam facilis et officia qui",
    "completed": false
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
  },

  computed:{
    fullName() {
        return `${this.user.first_name} ${this.user.last_name}`
    },

    uncompletedTodos() {
    return this.todos.filter(todo => !todo.completed);
    //Pede para retornar as todos que não estão completadas
    },

    completedTodos() {
    return this.todos.filter(todo => todo.completed);
    //Pede para retornar as todos estão completadas
    },
  }, 

  methods: {
        
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