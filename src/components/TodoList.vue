<template>
  <div class="wrap_list">
    <ul class="list">
      <todo-item
        v-for="todo in propTodosItem"
        :todoItem="todo"
        :key="todo.id"
        @isDone="emitState"
      />
    </ul>
    <div class="util" v-show="propTodosItem.length">
      <div class="count" >
        <em>{{ propTodosItem.length }}</em>
        <span v-if="propTodosItem.length < 2">item left</span>
        <span v-else>items left</span>
      </div>
      <ul class="filter">
        <li>
          <button type="button">all</button>
        </li>
        <li>
          <button type="button">active</button>
        </li>
        <li>
          <button type="button">complete</button>
        </li>
      </ul>
      <button type="button">clear completed</button>
    </div>
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem.vue'

export default {
  name: 'TodoList',
  components: {
    TodoItem
  },
  computed: {
    
  },
  props: ['propTodosItem'],
  methods: {
    emitState (bool, index) {
      this.$emit('isDone', bool, index);
    }
  }
}
</script>

<style lang="scss">
ul {
  list-style: none;
}
.util,
.filter {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.filter {
  column-gap: 20px;

  button {
    width: 60px;
  }
}
</style>