<template>
  <div id="app">
    <div class="main">
      <todoTitle/>
      <todos v-bind:todos="todos" v-on:delTodo="deleteTodo"></todos>
      <addItem v-on:add-item="addItem" />
    </div>
  </div>
</template>


<script>
import todoTitle from  './components/TodoTitle'
import todos from './components/Todos'
import addItem from './components/AddItem'

  export default {
    name: 'app',
    data() {
      return {
        todos: [
          {
            id: 1,
            title: "Complete assigned project",
            completed: true
          },
          {
            id: 2,
            title: "Go to University class",
            completed: false
          },
          {
            id: 3,
            title: "Go to super-shop",
            completed: false
          }
        ]
      }
    },
    methods: {
      deleteTodo(id) {
        this.todos = this.todos.filter(todo => todo.id !== id);
      },
      addItem(newItem) {
        this.todos = [...this.todos, newItem]
      }
    },
    components: {
      todoTitle, todos, addItem
    }
  }
</script>


<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
  .main {
    width: 40%;
    margin: 0 auto;
    min-height: 450px;
    margin-top: 4rem;
    padding: 3rem 5rem;
    background: rgb(59, 199, 134);
  }
</style>