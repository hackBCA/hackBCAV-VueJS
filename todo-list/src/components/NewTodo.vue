<template>
  <form @submit.prevent="addTodo">
    <b-row>
      <b-col>
        <b-form-input
          v-model="todo.name"
          name="todo"
          placeholder="Add a Todo..."
          required
        />
      </b-col>
      <b-col>
        <b-form-input
          v-model="todo.tag"
          name="tag"
          placeholder="Add a Tag..."
        />
      </b-col>
      <b-col>
        <b-button type="submit" value="Submit">Add Todo</b-button>
      </b-col>
    </b-row>
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
