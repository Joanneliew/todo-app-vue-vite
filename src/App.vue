<template>
  <div>
    <h1>Todo List</h1>
    <todo-form @addNew="addTodo"></todo-form>
    <h2>{{ listSummary }}</h2>
    <div>
      <todo-item v-for="(item, index) in todos" :key="index" :label="item.label" :done="item.done" :id="index" @changed="updateStatus(index)"></todo-item>
    </div>
  </div>
</template>

<script>
import TodoItem from "./components/TodoItem.vue"
import TodoForm from "./components/TodoForm.vue"

export default {
  name: 'App',
  components: {
    TodoItem,
    TodoForm,
  },
  data(){
    return {
      todos: [
        {
          label: "task 1",
          done: false,
        },
        {
          label: "task 2",
          done: false,
        },
      ]
    }
  },
  methods: {
    addTodo(value) {
      this.todos.push({
        label: value,
        done: false
      })
    },
    updateStatus(index){
      this.todos[index].done = !this.todos[index].done
    }
  },
  computed: {
    listSummary() {
      const doneLen = this.todos.filter((item) =>item.done).length
      return `${doneLen} out of ${this.todos.length} items completed`
    }
  }
}
</script>