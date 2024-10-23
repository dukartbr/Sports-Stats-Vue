<script setup>
import SearchBoxItem from "./SearchBoxItem.vue";
</script>

<style scoped>
#searchBox {
  position: absolute;
  left: calc(50% - (35vw / 2));
  top: 3rem;
  width: 35vw;
  max-width: 800px;
  min-height: 30vh;
  max-height: 80vh;
  background-color: #455552;
  border: 2px solid #52ffe2;
  box-shadow: 0px 15px 30px #000;
  overflow: scroll;
  padding: 10px 0px;
  border-radius: 16px;
  transition: height 0.25s;
}
</style>

<template>
  <div id="searchBox">
    <div v-for="res in searchResults">
      <SearchBoxItem :title="res.title" :body="res.body" :id="res.id" />
    </div>
  </div>
</template>

<script>
export default {
  props: ["searchResults"],
  created() {
    console.log("searchResults", this.searchResults);
  },
  watch: {
    searchResults: function (val) {
      console.log("searchResults", val);
    },
  },
};
</script>
