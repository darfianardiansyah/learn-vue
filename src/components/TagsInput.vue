<template>
  <div v-for="(tag, index) in tags" :key="index">
    {{ index + " : " + tag }}
    <a @click.prevent="removeTag(index)" href="#">x</a>
  </div>
  <!-- <hr />
  {{ newTag }} -->
  <input type="text" v-model.trim="newTag" @keydown.enter="addNewTag" @keydown.delete="removeLastTag"
    @keydown.tab.prevent="addNewTag"
    :class="{ 'tag-exists': tags.includes(newTag) }"/>
</template>

<script>
export default {
  data: () => ({
    tags: ["vue", "react", "angular"],
    newTag: "",
  }),
  methods: {
    addNewTag() {
      if (this.newTag) {
        this.tags.push(this.newTag);
        this.newTag = "";
      }
    },
    removeTag(index) {
      this.tags.splice(index, 1);
    },
    removeLastTag() {
      if (this.tags.length > 0) {
        this.tags.pop();
      }
    }
  },
};
</script>
<style scoped>
button {
  background-color: rgb(42, 95, 42);
  color: white;
}
.tag-exists {
  color:red;
  text-decoration: line-through;
}
</style>
