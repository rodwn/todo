<template>
  <div class="wrap_input">
    <div class="checkbox">
      <label for="chkAll">전체 선택</label>
      <input type="checkbox" id="chkAll">
    </div>
    <!-- <input type="text" @keyup.enter="registerTodo"> -->
    <v-text-field
      label="to do........"
      @keyup.enter="registerTodo"
    ></v-text-field>
  </div>
</template>

<script>
export default {
  // data () {
  //   return {
  //     value: '',
  //   }
  // } ,
  name: 'TodoInput',
  methods: {
    registerTodo (e) {
      console.log('this is Todo Input', e.target);
      this.$emit('registerTodo', e.target.value);
      e.target.value = '';
    }
  }
}
</script>

<style lang="scss" scoped>
.wrap_input {
  display: flex;

  .checkbox {
    
  }
}
</style>