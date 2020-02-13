<template>
  <div id="app">
    <b-container>
      <Header />
      <TodoContainer />
    </b-container>
  </div>
</template>

<script>
  import TodoContainer from '@/components/TodoContainer.vue';
  import Header from '@/components/layout/Header.vue';
  export default {
    name: 'App',
    components: {
      TodoContainer,
      Header,
    },
  };
</script>

<style lang="scss">
  @import '@/assets/styles/main.scss';
</style>
