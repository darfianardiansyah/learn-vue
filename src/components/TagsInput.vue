<template>
  <div v-for="(tag, index) in tags" :key="index">{{ index + " : " + tag }}</div>
  <hr />
  {{ newTag }}
  <input
    type="text"
    v-model.trim="newTag"
    @keydown.enter="tags.push(newTag)"
    @keydown.tab.prevent="tags.push(newTag)"
  />
</template>

<script>
export default {
  data: () => ({
    tags: ["vue", "react", "angular"],
    newTag: "preact",
  }),
};
</script>
<style>
button {
  background-color: rgb(42, 95, 42);
  color: white;
}
</style>
