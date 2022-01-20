<template>
  <div id="todo_box">
    <TodoInput @registerTodo="registerTodo" />
    <TodoList :propTodos="propTodos" />
  </div>
</template>

<script>
import TodoInput from '@/components/TodoInput.vue'
import TodoList from '@/components/TodoList.vue'

export default {
  name: 'Todo',
  props: ['propTodos'],
  components: {
    TodoInput,
    TodoList,
  },
  methods: {
    registerTodo (val) {
      console.log('this is Todo');
      this.$emit('registerTodo', val)
    }
  }
}
</script>

<style>

</style>