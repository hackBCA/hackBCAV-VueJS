<template>
  <div>
    <button v-on:click="addAll">Show All</button>
    <div v-for="tag in tags" :key="tag">
      <input :value="tag" v-model="selected" v-on:change="updateTags" type="checkbox" :id="tag" />
      <label :for="tag">{{ tag }}</label>
    </div>
  </div>
</template>

<script>
export default {
  name: "TagSelector",
  data: () => {
    return {
      selected: []
    };
  },
  props: {
    tags: Array
  },
  methods: {
    updateTags() {
      this.$emit("update-tags", this.selected);
    },
    addAll() {
      this.selected = this.tags;
      this.updateTags();
    }
  }
};
</script>

<style lang="scss" scoped></style>
