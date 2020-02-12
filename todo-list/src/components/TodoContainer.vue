<template>
  <div>
    <Todos :todos="this.todos" v-on:delete-todo="deleteTodo" />
    <NewTodo v-on:add-todo="addTodo" />
  </div>
</template>

<script>
  import Todos from '@/components/Todos.vue';
  import NewTodo from '@/components/NewTodo.vue';
  import shortid from 'shortid';
  export default {
    name: 'TodoContainer',
    components: {
      Todos,
      NewTodo,
    },
    data: () => {
      return {
        todos: [],
      };
    },
    methods: {
      addTodo(todo) {
        var newTodo = { ...todo, completed: false, _id: shortid.generate() };
        this.todos.push(newTodo);
      },
      deleteTodo(todoId) {
        this.todos.splice(
          this.todos.findIndex(el => el._id === todoId),
          1,
        );
      },
    },
  };
</script>

<style lang="scss" scoped></style>
