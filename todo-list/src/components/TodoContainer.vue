<template>
  <div>
    <Todos :todos="this.todos" />
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
        var newTodo = { ...todo, _id: shortid.generate() };
        this.todos.push(newTodo);
      },
    },
  };
</script>

<style lang="scss" scoped></style>
