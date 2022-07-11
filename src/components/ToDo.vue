<template>
  <div >
    <h1>{{message}}</h1>
    <h1>{{count}}</h1>
    <button v-on:click="countUp">Hochzählen</button>
  </div>
</template>

<script>
export default {
  name: 'ToDo',
  data: function() {
    return {
      message: "Hallo ToDo",
      count: 0,
    }
  },
  methods: {
    countUp(){
      this.count++;
    }
  }
}
</script>

