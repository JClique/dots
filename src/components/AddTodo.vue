<template lang="html">
  <div>
    <form @submit="addTodo">
      <input type="text" name="title" v-model="title" placeholder="Add Item..." autocomplete="off">
      <button type="submit">Add</button>
    </form>
  </div>
</template>

<script>
import {v4 as uuid} from 'uuid';

export default {
  name: "AddTodo",
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      if (this.title !== '') {     
        const newTodo = {
          id: uuid(),
          title: this.title,
          completed: false,
        }
        // Send up to parent
        this.$emit('add-todo', newTodo);
        this.title = '';
      }
    }
  }
}
</script>

<style lang="css" scoped>

form {
  display: flex;
  appearance: none;
}

input {
  flex: 10;
  font-size: 1em;
  padding: .5em;
  background-color: var(--white);
  color: var(--black);
}

button {
  flex: 2;
  border-left: 5px solid var(--black);
}

</style>
