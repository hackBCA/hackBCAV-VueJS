<template>
  <form @submit.prevent="addTodo">
    <input
      type="text"
      v-model="todo.name"
      name="todo"
      placeholder="Add a Todo..."
      required
    />
    <input
      type="text"
      v-model="todo.tag"
      name="tag"
      placeholder="Add a Tag..."
    />
    <input type="submit" value="Submit" class="btn" />
  </form>
</template>

<script>
  export default {
    name: 'NewTodo',
    data: () => {
      return {
        todo: { name: '', tag: '' },
      };
    },
    methods: {
      addTodo: function() {
        this.$emit('add-todo', this.todo);
        this.todo.name = '';
        this.todo.tag = '';
      },
    },
  };
</script>

<style lang="scss" scoped>
  input:invalid {
    box-shadow: none !important;
  }
</style>
