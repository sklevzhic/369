<template>
  <div>
    <ul id="todolist">
      <TodoItem
        v-on:remove-todo="removeToDo"
        v-for="todo of todos"
        :todo="todo"
        :key="todo.id"
       />
       <TodoItemNew 
        v-on:add-todo="addToDo"
       />
    </ul>
    <Modal />
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem';
import TodoItemNew from '@/components/TodoItemNew';
import Modal from '@/components/Modal';

export default {
  props: ['todos'],
  methods: {
    removeToDo: function(id) {
      this.$emit('remove-todo', id)
    },
    addToDo: function(todo) {
      this.todos.push(todo)
    }
  },
  components: {
    TodoItem,
    TodoItemNew,
    Modal
  }
}



</script>

<style lang="scss" scoped>
    $border-color: #e6e6e6;

  ul {
    list-style: none;
    margin: 0;
    padding: 0;
    width: 80vw;
    margin: 0 auto;
    
  }


  li  {
    display: flex;
    justify-content: space-between;
    border: 1px solid $border-color;
    margin-bottom: 5px;
    padding: 5px;

    &.done {
      background: red;
    }

    &:hover {
      background: $border-color
    }
    
  }

</style>