<template>
  <div v-for="(tag, index) in tags" :key="index">{{ index + " : " + tag }}</div>
  <input
    type="text"
    :value="newTag"
    @keydown.enter="tags.push($event.target.value)"
    @keydown.tab.prevent="tags.push($event.target.value)"
  />
  <!-- <button v-on:click="tags.push(newTag)">add</button> -->
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
