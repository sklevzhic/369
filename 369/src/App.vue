<template>
  <div id="app">
    <h1>Todo List</h1>
    <TodoList 
      @remove-todo="removeToDo"
      v-bind:todos='todos'
    />
  </div>
</template>

<script>
import TodoList from '@/components/TodoList'

export default {
  name: 'App',
  data() {
    return {
      todos: [
        {id: 1, title:'Купить1', descr: "Купить111", completed: false},
        {id: 2, title:'Купить2', descr: "22222", completed: false},
        {id: 3, title:'Купить3', descr: "333333333", completed: false},
        {id: 4, title:'Купить4', descr: "44444444", completed: false},
        {id: 5, title:'Купить5', descr: "5555555", completed: false}
      ]
    }
  },
  components: {
    TodoList
  }, 
  methods: {
    removeToDo(id) {
      this.todos = this.todos.filter(t => t.id !== id)
    }
  }
}
</script>

<style lang="scss">
  $primary-color: black;
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: $primary-color;
  margin-top: 60px;
}
</style>
