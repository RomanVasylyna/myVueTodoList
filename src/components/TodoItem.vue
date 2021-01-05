<template>
 <div class="allTodos">
    
   <h3 class="todo" :class="{'is-completed' : todo.completed}">
       
   <input type="checkbox" @change="markCompleted"> 

   {{ todo.title }} 
   
   <!-- We don't have an access to todos array from components directly
   We could've used props however it's better to emit an event from child
   component to parent component and change it in the App.vue
    -->
    
   <span class="del-btn" @click="$emit('removeItem', todo.id)">x</span>

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

removeItem() {
alert('fsdfsd');    
}


},

}
</script>

<style scoped>

.del-btn{
background: #fff;    
border: 1.2px solid red;
color: red;
padding: 1.5px 8px;
border-radius: 50%;
cursor: pointer;
float:right;
font-weight: bold;
}

.del-btn:hover{
background: red;
color: #fff;
}

/* If todo is checked */
.is-completed{
text-decoration: line-through;    
}

.allTodos{
background: #fff;    
width: 50%;
padding: 5px 10px;
}

.todo{
background:#fff;    
border-radius: 5px;
border: 1px solid gray;
padding: 12px;
width: 60%;
}

/* h3{
padding: 5px 0px; 
border: 1.5px solid gray;  
} */


</style>
