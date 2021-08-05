<template>
  <h1>To-do List - VueJS</h1>
  <Todo />
</template>

<script>
import Todo from './components/Todo.vue'

export default {
  name: 'App',
  components: {
    Todo
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
h1{
  color: rgb(11, 8, 63);
}
</style>
