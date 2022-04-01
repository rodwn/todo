<template>
  <div class="wrap_todo">
    <TodoInput @todoInputFirst="emitTodoValue" />
    <TodoList :propTodosItem="propTodos" @isDone="emitState" />
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
    emitTodoValue (val) {
      // console.log('this is Todo');
      this.$emit('todoVal', val)
    },
    emitState (bool, index) {
      this.$emit('isDone', bool, index)
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