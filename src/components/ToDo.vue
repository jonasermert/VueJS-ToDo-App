<template>
  <div class="flex justify-between items-center py-2 px-2" :class="{'bg-green-600': this.todo.done, 'bg-red-600: !todo.todo.done'}" >
    <!--
    <h1>{{message}}</h1>
    <h1>{{count}}</h1>
    <button v-on:click="countUp">Hochzählen</button>
    -->
    <h1 class="cursor-pointer" @click="toggleToDo">{{todo.todo}}</h1>
    <button class="bg-black py-1 px-1 rounded" @click="removeToDo">Delete ToDo</button>
  </div>
</template>

<script>
export default {
  name: 'ToDo',
  props: ["todoprop", "todoindex"],
  data: function() {
    return {
      /*
      message: "Hallo ToDo",
      count: 0,
      */
     todo: this.todoprop,
    };
  },
  methods: {
    /*
    countUp(){
      this.count++;
    }
    */
    toggleToDo(){
      // console.log(this.todoindex);
      this.$emit("toggleDone-index", this.todoindex);
    },
    removeToDo() {
      this.$emit("removetodo-index", this.todoindex);
    }



  }
}
</script>

