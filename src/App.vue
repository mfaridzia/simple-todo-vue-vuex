<template>
  <div id="app" class="container">
    <completed-todos></completed-todos>
    <get-todo></get-todo>
    <current-todos></current-todos>
  </div>
</template>

<script>
import GetTodo from './components/GetTodo'
import CurrentTodos from './components/CurrentTodos'
import CompletedTodos from './components/CompletedTodos'

export default {
  components: {
    GetTodo,
    CurrentTodos,
    CompletedTodos
  }
}
</script>

<style>
body {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
}
</style>
