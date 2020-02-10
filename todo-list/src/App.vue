<template>
  <div id="app">
    <Todo todo="Hello, World!"></Todo>
    <Todo todo="Hello Again!" />
  </div>
</template>

<script>
import Todo from "@/components/Todo.vue";
export default {
  name: "App",
  components: {
    Todo
  }
};
</script>

<style lang="scss">
</style>
