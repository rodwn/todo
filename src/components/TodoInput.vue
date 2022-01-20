<template>
  <div class="wrap_input">
    <div class="checkbox">
      <label for="chkAll">전체 선택</label>
      <input type="checkbox" id="chkAll">
    </div>
    <div class="input_field">
      <input type="text" @keyup.enter="registerTodo">
    </div>
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

<style>

</style>