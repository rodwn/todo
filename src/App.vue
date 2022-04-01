<template>
  <div id="app">
    <header>
      <h1>{{ title }}</h1>
    </header>
    <v-divider></v-divider>
    <main>
      <Todo
        @todoVal="registerTodo"
        @isDone="updateStat"
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
      // console.log('this is App');
      this.todos.push({isDone: false, item: val});
    },
    updateStat (bool, index) {
      console.log(index);
      this.todos[0].isDone= bool;
    }
  }
}
</script>

<style>
html {
  margin: 0;
  padding: 0;
  background-color: #f5f5f5;
}
header {
  text-align: center;
  padding: 20px 0;
}
</style>
