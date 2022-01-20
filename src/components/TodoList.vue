<template>
  <div class="wrap_list">
    <ul class="list">
      <TodoItem />
    </ul>
    <div>
      {{propTodos}}
    </div>
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem.vue'

export default {
  name: 'TodoList',
  props: ['propTodos'],
  components: {
    TodoItem
  }
}
</script>

<style>
.list {
  list-style: none;
}
</style>