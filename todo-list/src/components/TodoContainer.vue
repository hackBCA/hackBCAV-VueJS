<template>
  <div>
    <Todos :todos="this.todos" />
    <NewTodo v-on:add-todo="addTodo" />
  </div>
</template>

<script>
import Todos from "@/components/Todos.vue";
import NewTodo from "@/components/NewTodo.vue";
export default {
  name: "Todo Container",
  components: {
    Todos,
    NewTodo
  },
  data: () => {
    return {
      todos: ["Hello, World!", "Hello Again!", "yoyoyo"]
    };
  },
  methods: {
    addTodo(todo) {
      this.todos.push(todo);
    }
  }
};
</script>

<style lang="scss" scoped>
</style>
