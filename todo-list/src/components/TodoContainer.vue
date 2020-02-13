<template>
  <b-container>
    <TagSelector :tags="tags" v-on:update-tags="updateTags" />
    <hr />
    <Todos :todos="todos" :tags="selectedTags" v-on:delete-todo="deleteTodo" />
    <hr />
    <NewTodo v-on:add-todo="addTodo" />
  </b-container>
</template>

<script>
  import Todos from '@/components/Todos.vue';
  import NewTodo from '@/components/NewTodo.vue';
  import TagSelector from '@/components/TagSelector.vue';
  import shortid from 'shortid';
  export default {
    name: 'TodoContainer',
    components: {
      Todos,
      NewTodo,
      TagSelector,
    },
    data: () => {
      return {
        todos: [],
        selectedTags: [],
      };
    },
    methods: {
      addTodo(todo) {
        var newTodo = { ...todo, completed: false, _id: shortid.generate() };
        this.todos.push(newTodo);
      },
      deleteTodo(todoId) {
        this.todos.splice(
          this.todos.findIndex(el => el._id === todoId),
          1,
        );
      },
      updateTags(tags) {
        this.selectedTags = tags;
      },
    },
    computed: {
      tags: function() {
        return Array.from(new Set(this.todos.map(x => x.tag)));
      },
    },
  };
</script>

<style lang="scss" scoped>
  @import '@/assets/styles/main.scss';
  .container {
    padding: 20px;
    // height: 60%;
    background-color: $nord3;
  }
</style>
