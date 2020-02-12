<template>
  <div>
    <Todo
      v-for="todo in todos"
      :todo="todo"
      :key="todo._id"
      v-on:delete-todo="deleteTodo"
    />
  </div>
</template>

<script>
  import Todo from '@/components/Todo.vue';
  export default {
    name: 'Todos',
    components: {
      Todo,
    },
    props: {
      todos: Array,
    },
    methods: {
      deleteTodo(todoId) {
        this.$emit('delete-todo', todoId);
      },
    },
  };
</script>

<style lang="scss" scoped></style>
