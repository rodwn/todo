<template>
  <div id="app">
    <header>
      <h1>{{ title }}</h1>
    </header>
    <main>
      <Todo
        @registerTodo="registerTodo"
        :propTodos="todos"
        />
    </main>
  </div>
</template>

<script>
import Todo from '@/components/Todo.vue'

export default {
  data () {
    return {
      title: 'title!',
      todos: [],
    }
  },
  name: 'App',
  components: {
    Todo
  },
  methods: {
    registerTodo (val) {
      console.log('this is App');
      this.todos.push(val);
    }
  }
}
</script>

<style>
html {
  margin: 0;
  padding: 0;
  background-color: #ccc;
}
header {
  text-align: center;
}
</style>
