<template>
  <div>
    <h3 v-bind:class="{'isCompleted': todoItem.completed}">
      <input type="checkbox" v-on:change="changeValue">
      {{todoItem.title}}
      <button @click="$emit('delTodo', todoItem.id)">X</button>
    </h3>
  </div>
</template>


<script>
export default {
  name: 'todoItem',
  props: ["todoItem"],
  methods: {
    changeValue() {
      this.todoItem.completed = !this.todoItem.completed;
    }
  }
}
</script>


<style scoped>
  .isCompleted {
    text-decoration: line-through;
  }
  h3 {
    padding: 5px;
  }
  button {
    padding: 1px 8px;
    background: rgb(216, 66, 66);
    border: none;
    cursor: pointer;
    color: #fff;
  }
</style>