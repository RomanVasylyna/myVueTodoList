<template>
 <div class="container">

   <h3 class="todo" :class="{'is-completed' : todo.completed}">

   <input type="checkbox" @change="markCompleted">

   {{ todo.title }}

   <!-- We don't have an access to todos array from components directly
   We could've used props however it's better to emit an event from child
   component to parent component and change it in the App.vue
   -->

   <span class="del-btn" @click="$emit('removeItem', todo.id)">Delete</span>

   </h3>

</div>
</template>

<script>
export default {
name: 'TodoItem',

props: ['todo'],

methods: {
markCompleted() {
this.todo.completed = !this.todo.completed;
},


},

}
</script>

<style scoped>


.del-btn:hover{
background: red;
color: #fff;
}

/* If todo is checked */
.is-completed{
text-decoration: line-through;
color: green;
}

/* Phones */
@media (max-width: 690px) {

.todo{
display:flex;
flex-direction: column;  
align-items: center;
background:#fff;
border-radius: 5px;
border: 1px solid gray;
padding: 12px;
margin: 12px;
word-wrap: break-word;
}

.del-btn{
background: #fff;
border: 1.2px solid red;
color: red;
padding: 1.5px 7px;
border-radius: 20px;
cursor: pointer;
float:right;
font-weight: bold;
font-size: 0.9rem;
}

}

/* Regular Desktops */

.todo {
background:#fff;
border-radius: 5px;
border: 1px solid gray;
padding: 12px;
margin: 12px;
}

.del-btn{
background: #fff;
border: 1.2px solid red;
color: red;
padding: 1.5px 8px;
border-radius: 20px;
cursor: pointer;
float:right;
font-weight: bold;
font-size: 0.9rem;
}


</style>
