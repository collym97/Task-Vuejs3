<template>
  <Task />
</template>

<script>
import Task from './components/task.vue'

export default {
  name: 'App',
  components: {
    Task,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body {

  background-color: rgb(255, 255, 255);
}
</style>

