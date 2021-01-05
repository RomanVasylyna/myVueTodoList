<template>
  <div id="app">
   <!-- <Header /> -->
  <div class="allTodos">
    <h1>To-Do List</h1>
    <AddTodo :todos="todos" @addTodo="addTodo"/>
   <Todos :todos="todos" @removeItem="removeItem"/>
   </div>
  </div>
</template>


<script>
// Import Elements
// import Header from './styling/Header.vue';
import AddTodo from './components/AddTodo.vue';
import Todos from './components/Todos.vue';

export default {
  name: 'App',

  data() {
  return {

  todos: [

  {
   id: '1',
   title: 'Todo One',
   completed: false,
  },

  {
   id: '2',
   title: 'Todo Two',
   completed: true,
  },

  {
   id: '3',
   title: 'Todo Three',
   completed: false,
  },

  ],

  }
  },

  components: {
  // Header,
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

}
</script>

<style>

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
padding: 18px;
margin: 50px auto;
border-radius: 20px;
}

.allTodos h1{
text-align: center;
margin-bottom: 5px;
}

</style>
