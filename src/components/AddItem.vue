<template>
  <div>
    <form @submit="addItem">
      Add new todo item:
      <input type="text" v-model="title">
      <input type="submit" value="Add">
    </form>
  </div>
</template>


<script>
import uuid from 'uuid';
export default {
  name: 'AddItem',
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addItem(e) {
      e.preventDefault();
      const newItem = {
        id: uuid.v4(),
        title: this.title,
        completed: false
      }
      // send up to parent
      this.$emit('add-item', newItem);
      this.title='';
    }
  }
}
</script>


<style  scoped>
form {
  padding: 10px 0 0 5px;
}
form input {
  padding: 4px 7px;
}
</style>