<template>
  <div>
    <input type="checkbox" :id="id" :checked="isDone" @change="$emit('changed')">
    <label :for="id">{{ label }}</label>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: {
    label: {
      required: true,
      type: String,
    },
    done: {
      default: false,
      type: Boolean
    },
    id: { 
      required: true, 
      type: Number 
    },
  },
  data(){
    return {
      isDone: this.done,
      // id: crypto.randomUUID()
    }
  }
}
</script>