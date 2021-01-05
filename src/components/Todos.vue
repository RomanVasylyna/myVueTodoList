<template>
 <div>
     <div :key="todo.id" v-for="todo in todos">
         <!-- Here we grab emit event from child element -->
      <TodoItem :todo="todo" @removeItem="$emit('removeItem', todo.id)"/>
     </div>
 </div>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
name : 'Todos', 

props: ['todos'],

components: {
TodoItem    
}

}
</script>

<style scoped>

</style>
