<template>
  <div id="app">
   <Header />
   <AddTodo />
   <Todos :todos="todos" />
  </div>
</template>


<script>
// Import Elements
import Header from './styling/Header.vue';
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
  Header, 
  AddTodo,
  Todos,
  },

  methods: {
  removeItem() {
    
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
}

</style>
