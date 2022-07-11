<template>
  <div class="bg-gray-600 text-white w-1/2 m-auto mt-12">
    <div class="text-center border-b-2 border-black py-4">
      <h1 class="text-3xl py-4">Meine ToDo's</h1>
      <p class="text-xl">Offene ToDo's: {{todos.length}}</p>
    </div>
    
    <div v-for="todo in todos" :key="todo.todo">
      <ToDo :todoprop="todo.todo"/>
      <!--
      <ToDo :todoprop="todos[0].todo"/>
      <ToDo :todoprop="todos[1].todo"/>
      <ToDo :todoprop="todos[2].todo"/>
      -->
    </div>


  </div>
  
</template>

<script>
import ToDo from './components/ToDo.vue'

export default {
  name: 'App',
  data() {
    return {
      todos: [
        {todo:"programming", done: false},
        {todo:"shopping", done: false},
        {todo:"sport", done: false},
      ],
    }
  },
  components: {
    ToDo,
  }
}
</script>
