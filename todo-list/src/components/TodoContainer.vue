<template>
  <div>
    <Todos :todos="this.sampleTodos" />
  </div>
</template>

<script>
import Todos from "@/components/Todos.vue";
export default {
  name: "Todo Container",
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

<style lang="scss" scoped>
</style>
