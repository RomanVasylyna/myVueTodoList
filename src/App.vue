<template>
  <div id="app">

   <!-- All Todos Container -->
  <div class="allTodos">
    <h1>To-Do List</h1>
    <AddTodo :todos="todos" @addTodo="addTodo"/>
   <Todos :todos="todos" @removeItem="removeItem"/>
   </div>

  </div>
</template>


<script>
// Import Elements
import AddTodo from './components/AddTodo.vue';
import Todos from './components/Todos.vue';

export default {
  name: 'App',

  data() {
  return {

  todos: [],

  }
  },

  components: {
  AddTodo,
  Todos,
  },

  methods: {
  removeItem(id) {
  this.todos = this.todos.filter(todo => todo.id != id);
  },

  addTodo(newTodo) {
  this.todos = [...this.todos, newTodo];
  }
  },

  created() {
  fetch('https://jsonplaceholder.typicode.com/todos')
  .then(res => res.json())
  .then(resJson => {
  resJson.length = 3;
  this.todos = resJson;
  })
  .catch(err => console.log(err));
  }

}
</script>

<style>

/* General Styling For All Elements */
*{
box-sizing: border-box;
margin: 0;
padding: 0;
}

body{
background: linear-gradient(to left, #e66465, #9198e5);
font-family: sans-serif;
}

.allTodos{
background: white;
width: 50%;
padding: 20px;
margin: 50px auto;
border-radius: 20px;
}

.allTodos h1{
text-align: center;
margin-bottom: 5px;
font-size: 2rem;
}


/* Phones */
@media (max-width: 690px) {

.allTodos{
background: white;
width: 60%;
padding: 7px;
margin: 50px auto;
border-radius: 20px;
}

.allTodos h1{
text-align: center;
margin-bottom: 5px;
font-size: 1.5rem;
}

}

/* Ipad and other tablets*/
@media only screen and (max-width: 800px) and (min-width: 700px) {

.allTodos{
background: white;
width: 70%;
padding: 7px;
margin: 50px auto;
border-radius: 20px;
}

.allTodos h1{
text-align: center;
margin-bottom: 5px;
font-size: 1.5rem;
}

}

/* Ipad Pro */
@media only screen and (max-width: 1100px) and (min-width: 1000px) {

.allTodos{
background: white;
width: 70%;
padding: 9px;
margin: 50px auto;
border-radius: 20px;
}

.allTodos h1{
text-align: center;
margin-bottom: 5px;
font-size: 2rem;
}

}




</style>
