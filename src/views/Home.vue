<template>
  <div id="app">
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos
      v-bind:todos="todos"
      v-on:del-todo="deleteTodo"
    />
  </div>
</template>

<script>

import AddTodo from '../components/AddTodo';
import Todos from '../components/Todos';

export default {
  name: 'Home',
  components: {
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Do thing 1",
          completed: false,
        },
        {
          id: 2,
          title: "Do thing 2",
          completed: false,
        },
        {
          id: 3,
          title: "Do thing 3",
          completed: false,
        },
        {
          id: 4,
          title: "Do thing 4",
          completed: false,
        },
        {
          id: 5,
          title: "Do thing 5",
          completed: false,
        },
      ]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    }
  }
}
</script>
