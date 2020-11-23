<template>
  <div id="app">
    <div class="todo-app">
      TODO APP
    </div>
  <img src="./assets/logo.png">
    <todoList>Todo list</todoList>
    

    </div>
</template>

<script>

import todoList from './components/todoList'




export default {
  name: 'app',

  components: {
    todoList,
  
  
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  font-size: 25px;
}
.todo-app{
  font-size: 85px;
}
</style>
