<template>
    ``<h1 id="fonttodo">My-Todo-s</h1>
      <div id="app">
        <TodoBoard :todos="todos" @addTodo="addTodo" @deleteTodo="deleteTodo" @changeStatusTodo="changeStatusTodo" />
      </div>
</template>

<script>
import TodoBoard from "./components/TodoBoard.vue";

export default {
  name: "App",
  components: {
    TodoBoard,
  },
  data() {
    return {
      todos: [],
    };
  },
  methods: {
    addTodo(newTodo) {
      this.todos.push(newTodo);
    },
    deleteTodo(todoId) {
      this.todos = this.todos.filter(todo => todo.id !== todoId);
    },
    changeStatusTodo(todoId) {
      const todoIndex = this.todos.findIndex(todo => todo.id === todoId);
      this.todos[todoIndex].completed = !this.todos[todoIndex].completed;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: black;
  margin-top: 30px;
}

#fonttodo {
  color: #7EC8E3;
}

</style>