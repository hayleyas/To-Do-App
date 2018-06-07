<template>
  <div id="app">
    <h1 class="ui dividing centered header">To Do List</h1>
    <div class='ui three column centered grid'>
      <div class='column'>
        <todo-list v-bind:todos="todos"></todo-list>
        <create-todo v-on:create-todo="createTodo"></create-todo>
      </div>
    </div>
  </div>
</template>

<script>
import sweetalert from 'sweetalert';
import TodoList from './components/TodoList';
import CreateTodo from './components/CreateTodo';
export default {
  name: 'app',
  components: {
    TodoList,
    CreateTodo,
  },
  data() {
    return {
      todos: [{
        title: 'New To Do List Item',
        project: 'Replace me with your first item.',
        done: false,
      }, {
        title: 'New To Do List Item',
        project: 'Replace me with your second item.',
        done: false,
      }, {
        title: 'New To Do List Item',
        project: 'Replace me with your third item.',
        done: false,
      }],
    };
  },
  methods: {
    createTodo(newTodo) {
      this.todos.push(newTodo);
      sweetalert('Success!', 'To-Do created!', 'success');
    },
  },
};
</script>