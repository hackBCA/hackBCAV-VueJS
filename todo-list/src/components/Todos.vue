<template>
  <b-row>
    <Todo
      v-for="todo in visibleTodos"
      :todo="todo"
      :key="todo._id"
      v-on:delete-todo="deleteTodo"
    />
  </b-row>
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
      tags: Array,
    },
    methods: {
      deleteTodo(todoId) {
        this.$emit('delete-todo', todoId);
      },
    },
    computed: {
      visibleTodos: function() {
        const visible = this.todos.filter(todo => this.tags.includes(todo.tag));
        return visible;
      },
    },
  };
</script>

<style lang="scss" scoped></style>
