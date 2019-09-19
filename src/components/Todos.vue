<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todos">
      <todoItem v-bind:todoItem="todo" v-on:delTodo="$emit('delTodo', todo.id)"></todoItem>
    </div>
  </div>
</template>

<script>
import todoItem from './TodoItem'

export default {
  name: 'todos',
  components: {
    todoItem
  },
  props: ["todos"]
}
</script>