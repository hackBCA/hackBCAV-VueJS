<template>
  <div class="todo-item" :class="{ completed: todo.completed }">
    <b-card no-body class="bg-dark text-light text-center card">
      <b-form-checkbox v-model="todo.completed">
        <span class="label" :class="{ completed: todo.completed }">{{
          todo.name
        }}</span>
      </b-form-checkbox>
      <span>{{ todo.tag }}</span>
      <b-button size="sm" v-on:click="deleteTodo" variant="danger">X</b-button>
    </b-card>
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
  .card {
    padding: 10px;
    margin: 20px;
    width: 300px;
    overflow: auto;
  }

  .label {
    font-size: 1.5em;
  }

  .btn {
    width: 10%;
  }
</style>
