<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Todos from './components/Todos';
import AddTodo from './components/AddTodo';

export default {
  name: 'App',
  components: {
      Header,
      Todos,
      AddTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Call Adam",
          completed: false
        },
        {
          id: 2,
          title: "Buy flowers",
          completed: true
        },
        {
          id: 3,
          title: "Send email to John",
          completed: true
        },
        {
          id: 4,
          title: "Walk dog",
          completed: false
        },
        {
          id: 5,
          title: "Fly to the Moon",
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id != id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo]
    }
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin-left: 7px;
    margin-right: 7px;
    padding: 0px;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 2;
  }

.btn {
        display: inline-block;
        border: none;
        background: #32cd32;
        color: #f0ffff;
        border-radius: 999px;
        text-align: center;
        cursor: pointer;
    }

.btn:hover {
  background: #228b22;
}
</style>
