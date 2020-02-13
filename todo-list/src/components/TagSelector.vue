<template>
  <div>
    <b-button v-on:click="addAll">Show All</b-button>
    <b-form-checkbox-group
      v-model="selected"
      :options="tags"
      name="tags"
    ></b-form-checkbox-group>
  </div>
</template>

<script>
  export default {
    name: 'TagSelector',
    data: () => {
      return {
        selected: [],
      };
    },
    props: {
      tags: Array,
    },
    methods: {
      updateTags() {
        this.$emit('update-tags', this.selected);
      },
      addAll() {
        this.selected = this.tags;
      },
    },
    watch: {
      selected: function() {
        this.updateTags();
      },
    },
  };
</script>

<style lang="scss" scoped></style>
