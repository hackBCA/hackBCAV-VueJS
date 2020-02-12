<template>
  <div>
    <Todo v-for="todo in todos" :todo="todo" :key="todo._id" />
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
  };
</script>

<style lang="scss" scoped></style>
