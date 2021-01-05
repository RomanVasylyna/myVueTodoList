<template>
<div>

   <form @submit="addItem">
      <input type="text" placeholder="Add Todo..." v-model="title">
   </form>

</div>
</template>

<script>
// Importing Tool to Generate Ids
import { v4 as uuidv4 } from 'uuid';

export default {
name: 'AddTodo',

props: ['todos'],

data() {
return {

title: '',

}
},

methods: {
addItem(e) {
// Prevent Form from Submitting
e.preventDefault();

// Add New Todo
let newTodo = {
id: uuidv4(),
title: this.title,
completed: false
};

// Push new Todo to Array with Todos
this.$emit('addTodo', newTodo);

// Clearing Input Field
this.title='';
}
},

}
</script>

<style scoped>

form{
text-align: center;
}

form input{
width: 45vw;
height: 7vh;
padding: 5px;
border-radius: 5px;
}



</style>
