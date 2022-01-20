<template>
  <div class="wrap_todo">
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

<style lang="scss" scoped>
.wrap_todo {
  width: 800px;
  margin: 0 auto;
}
</style>