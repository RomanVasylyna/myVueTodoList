<template>
<div>

   <form @submit="addItem">
      <input type="text" placeholder="Add Todo..." v-model="title">
   </form>

</div>
</template>

<script>

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

if(this.title != '') {

// if(this.title.length > 10) {
// this.title = this.title.slice(0, 10) + '...';
// }


// Add New Todo
let newTodo = {
id: this.todos.length + 1,
title: this.title,
completed: false
};

// Clearing Input Field
this.title='';

// Push new Todo to Array with Todos
this.$emit('addTodo', newTodo);

} else {
  alert('Todo Can\'t be empty!');
}

}
},

}
</script>

<style scoped>

/* All devices */
form{
text-align: center;
}

form input{
width: 45vw;
height: 6vh;
padding: 12px;
border-radius: 5px;
margin-bottom: 7px;
}


/* Phones */
@media (max-width: 690px) {

form input{
width: 45vw;
height: 7vh;
padding: 12px;
border-radius: 5px;
margin-bottom: 7px;
}

}

/* Ipad and other tablets*/
@media only screen and (max-width: 800px) and (min-width: 700px) {

form input{
width: 45vw;
height: 4vh;
padding: 12px;
border-radius: 5px;
margin-bottom: 10px;
}

}

/* Ipad Pro */
@media only screen and (max-width: 1100px) and (min-width: 1000px) {

form input{
width: 45vw;
height: 4vh;
padding: 12px;
border-radius: 5px;
margin-bottom: 10px;
}

}


</style>
