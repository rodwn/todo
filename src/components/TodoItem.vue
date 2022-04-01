<template>
  <li class="li">
    <v-checkbox
      v-model="checkbox"
    ></v-checkbox>
    <div class="content">
      {{ todoItem.item }}
    </div>
  </li>
</template>

<script>
export default {
  name: 'TodoItem',
  data () {
    return {
      checkbox: false
    }
  },
  props: ['todoItem'],
  watch: {
    checkbox () {
      this.$emit('isDone', this.checkbox);
    }
  },
  methods: {
   
  }
}
</script>

<style lang="scss">
.li {
  display: flex;
  align-items: center;
  column-gap: 9px;
  padding-left: 7px;

  .v-input {
    margin: 0;
    padding: 0;

    &__slot {
      margin: 0;
    }
    .v-messages {
      display: none;
    }
  }
}
</style>