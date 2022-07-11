<template>
  <div class="bg-gray-600 text-white w-1/2 m-auto mt-12">
    <div class="text-center border-b-2 border-black py-4">
      <h1 class="text-3xl py-4">Meine ToDo's</h1>
      <p class="text-xl" v-if="opentodos.length > 0">Offene ToDo's: {{opentodos.length}}</p>
      <p class="text-xl" v-else>There is nothing to do for you!</p>


      <div class="mt-4">
        <input type="text" class="py-2 w-2/3 text-black" v-model="newToDo"/>
        <button class="bg-blue-400 py-2 w-1/3" @click="addToDo">Add ToDo</button>
      </div>

    </div>
    
    <div v-for="(todo, index) in todos" :key="todo.todo">
      <ToDo :todoprop="todo" :todoindex="index" @toggleDone-index="toggleDone" @removetodo-index="deleteToDo"/>
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
      newToDo: "",
      todos: [
        {todo:"programming", done: false},
        {todo:"shopping", done: false},
        {todo:"sport", done: true},
      ],
    }
  },
  methods: {
    toggleDone(index) {
      this.todos[index].done = !this.todos[index].done;
    },
    deleteToDo(index) {
      this.todos.splice(index, 1);
    },
    addToDo(){
      if(this.newToDo.trim() === "") {
        return;
      }
      this.todos.push({todo:this.newToDo, done: false});
    },
  },
  computed: {
    opentodos() {
      const opentodos = this.todos.filter((todo) => {
        return !todo.done
      })
      return opentodos;
    }
  },
  components: {
    ToDo,
  }
}
</script>
