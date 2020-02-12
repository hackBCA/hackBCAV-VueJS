<template>
  <div class="todo-item">
    <h3>{{ todo.name }}</h3>
  </div>
</template>

<script>
  export default {
    name: 'Todo',
    props: {
      todo: Object,
    },
  };
</script>

<style lang="scss"></style>
