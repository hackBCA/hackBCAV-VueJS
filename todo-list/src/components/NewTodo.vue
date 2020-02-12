<template>
  <form @submit.prevent="addTodo">
    <input type="text" v-model="todo" name="todo" placeholder="Add a Todo..." />
    <input type="submit" value="Submit" class="btn" />
  </form>
</template>

<script>
export default {
  name: "NewTodo",
  data: () => {
    return {
      todo: ""
    };
  },
  methods: {
    addTodo: function() {
      this.$emit("add-todo", this.todo);
      this.todo = "";
    }
  }
};
</script>

<style>
</style>
