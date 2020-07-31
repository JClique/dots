<template lang="html">
  <li class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <label class="container">
      <input type="checkbox" v-on:change="markComplete">
      <span class="checkmark"></span>
    </label>
    <p>
      {{ todo.title }}
    </p>
    <button type="button" class="del"
    @click="$emit('del-todo', todo.id)">
    x
    </button>
  </li>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed
    },
  }
}
</script>

<style lang="css" scoped>

.todo-item {
  padding: 1em 1.5em;
  border-top: 1px var(--white) dotted;
  display: flex;
  justify-content: space-between;
  width: 100%;
}

.todo-item:first-child {
  border: 0;
}

.is-complete {
  opacity: 0.6;
}

.is-complete p {
  text-decoration: line-through;
}

.del {
  background: var(--lilac);
  color: var(--white);
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}

.del:hover {
  background: var(--lilac-dark);
}



/* Customize the label (the container) */
.container {
  display: block;
  position: relative;
  padding-left: 35px;
  margin-bottom: 12px;
  cursor: pointer;
  font-size: 22px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

/* Hide the browser's default checkbox */
.container input {
  position: absolute;
  opacity: 0;
  cursor: pointer;
  height: 0;
  width: 0;
}

/* Create a custom checkbox */
.checkmark {
  position: absolute;
  top: 0;
  left: 0;
  height: 25px;
  width: 25px;
  background-color: #eee;
  border-radius: 1em;
}

/* On mouse-over, add a grey background color */
.container:hover input ~ .checkmark {
  background-color: #ccc;
}

/* When the checkbox is checked, add a blue background */
.container input:checked ~ .checkmark {
  background-color: var(--spring);
}

/* Create the checkmark/indicator (hidden when not checked) */
.checkmark:after {
  content: "";
  position: absolute;
  display: none;
}

/* Show the checkmark when checked */
.container input:checked ~ .checkmark:after {
  display: block;
}

/* Style the checkmark/indicator */
.container .checkmark:after {
  left: 9px;
  top: 5px;
  width: 5px;
  height: 10px;
  border: solid white;
  border-width: 0 3px 3px 0;
  -webkit-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  transform: rotate(45deg);
}

</style>
