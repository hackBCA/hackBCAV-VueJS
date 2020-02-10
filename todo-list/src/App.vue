<template>
  <div id="app">
    <Todos :todos="this.sampleTodos" />
  </div>
</template>

<script>
import Todos from "@/components/Todos.vue";
export default {
  name: "App",
  components: {
    Todos
  },
  data: () => {
    return {
      sampleTodos: ["Hello, World!", "Hello Again!", "yoyoyo"]
    };
  }
};
</script>

<style lang="scss">
</style>
