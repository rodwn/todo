<template>
  <v-form class="wrap_input" @submit.prevent="todoInput" v-model="valid">
    <div class="checkbox">
      <input type="checkbox" id="chkAll">
      <label for="chkAll">전체 선택</label>
    </div>
    <!-- <input type="text" @keyup.enter="registerTodo"> -->
    <v-text-field
      label="to do........"
      v-model="inputText"
      :rules="todoRules"
      required
    ></v-text-field>
  </v-form>
</template>

<script>
export default {
  data () {
    return {
      valid: false,
      todoRules: [
        v => !!v || 'Todo is required',
      ],
      inputText: '',
    }
  },
  name: 'TodoInput',
  methods: {
    todoInput () {
      // console.log('this is Todo Input');
      if (!this.inputText.trim()) return;

      this.$emit('todoInputFirst', this.inputText);
      this.inputText = '';
    }
  }
}
</script>

<style lang="scss" scoped>
.wrap_input {
  display: flex;
  align-items: center;

  .checkbox {
    position: relative;
    
    input {
      position: absolute;
      top: 50%;
      left: 50%;
      border-radius: 0;
      border: 0;
      appearance: none;

      &:checked {
         + label {
           color: #000;
         }
      }
    }
    label {
      display: block;
      width: 40px;
      height: 40px;
      font-size: 0;
      color: #ccc;

      &::after {
        content: '';
        position: absolute;
        top: calc(50% - 11px);
        left: calc(50% - 8px);
        width: 15px;
        height: 15px;
        border-bottom: 4px solid;
        border-left: 4px solid;
        transform: rotate(-45deg);
      }
    }
  }
}
</style>