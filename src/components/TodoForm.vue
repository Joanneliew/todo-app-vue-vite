<template>
  <form @submit.prevent="onSubmit">
    <label for="new-todo-input"></label>
    <input type="text" id="new-todo-input" name="new-todo" autocomplete="off" v-model="value">
    <button type="submit">Add</button>
  </form>
</template>

<script>
export default {
  name: 'TodoForm',
  props: {
  },
  data(){
    return {
        value: "",
    }
  },
  methods: {
    onSubmit(){
        if (this.value === "") {
            return;
        }
        this.$emit("addNew", this.value);
        this.value = ""
    }
  }
}
</script>