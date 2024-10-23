<style scoped>
.searchBoxItem {
  padding: 5px 15px;
  display: flex;
  flex-direction: column;
  transition: background-color 0.25s;
}
.tag {
  color: #999;
}
.searchBoxItem:hover {
  background-color: #ff8352;
}

.searchBoxItem:hover .tag {
  color: #000;
}
</style>

<template>
  <div class="searchBoxItem">
    <span class="title">{{ title }}</span>
    <span class="tag">ID: {{ id }}</span>
  </div>
</template>

<script>
export default {
  props: ["title", "body", "id"],
};
</script>
