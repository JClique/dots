<template lang="html">
  <ul class="todo-list">
    <TodoItem
      v-bind:todo="todo"
      v-on:del-todo="$emit('del-todo', todo.id)"
      v-for="todo in todos"
      v-bind:key="todo.id"
    />
  </ul>
</template>

<script>
import TodoItem from './TodoItem'

export default {
  name: "Todos",
  components: {
    TodoItem
  },
  props: ["todos", "thisTodo"]
}
</script>

<style lang="css" scoped>

.todo-list {
  max-height: 70vh;
  overflow-y: scroll;
  margin-top: .25em;
  margin-bottom: .75em;
}

</style>
