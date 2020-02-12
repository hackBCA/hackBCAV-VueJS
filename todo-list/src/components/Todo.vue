<template>
  <div class="todo-item">
    <input type="checkbox" v-model="todo.completed" />
    <p :class="{ completed: todo.completed }">{{ todo.name }}</p>
    <button v-on:click="deleteTodo">X</button>
  </div>
</template>

<script>
  export default {
    name: 'Todo',
    props: {
      todo: Object,
    },
    methods: {
      deleteTodo() {
        this.$emit('delete-todo', this.todo._id);
      },
    },
  };
</script>

<style lang="scss" scoped>
  .completed {
    text-decoration: line-through;
  }
</style>
