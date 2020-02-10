<template>
  <div class="todo-item">
    <h3>{{todo}}</h3>
  </div>
</template>

<script>
export default {
  name: "Todo",
  props: {
    todo: String
  }
};
</script>

<style lang="scss">
</style>
