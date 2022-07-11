<template>
  <div >
    <!--
    <h1>{{message}}</h1>
    <h1>{{count}}</h1>
    <button v-on:click="countUp">Hochzählen</button>
    -->
    <h1>{{todo}}</h1>
  </div>
</template>

<script>
export default {
  name: 'ToDo',
  props: ["todoprop"],
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
  }
}
</script>

