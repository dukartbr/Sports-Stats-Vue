<script setup>
import SearchBox from "./components/SearchBox.vue";
</script>

<style scoped>
.header {
  display: flex;
  font-weight: bold;
  text-transform: uppercase;
  background-color: #52ffe2;
  padding: 1rem 3rem;
  justify-content: space-between;
  align-items: center;
}

.header h1 {
  font-size: 1.5rem;
  letter-spacing: 0.05rem;
}

.header #loginButton {
  border-radius: 1rem;
  padding: 0.5rem 2rem;
  border: none;
  background-color: #ff8352;
  text-transform: uppercase;
  font-weight: bold;
}

.searchInput {
  background-color: transparent;
  border: 2px solid #000;
  border-radius: 18px;
  width: 300px;
  padding: 8px;
}
</style>

<template>
  <div>
    <div class="header">
      <h1>Sports Stats UI</h1>
      <input
        type="text"
        v-model="query"
        @input="debouncedInput"
        class="searchInput"
      />
      <button id="loginButton">Login</button>
      <SearchBox v-if="showSearchModal" :searchResults="searchResults" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      query: null,
      timeout: null,
      showSearchModal: false,
      searchResults: [],
    };
  },
  methods: {
    makeRequest() {
      fetch("https://jsonplaceholder.typicode.com/posts")
        .then((res) => res.json())
        .then((res) => {
          this.searchResults = [...res];
        });
    },
    debouncedInput() {
      clearTimeout(this.timeout);
      if (this.query.length > 0) {
        this.showSearchModal = true;
        this.timeout = setTimeout(() => {
          this.makeRequest();
        }, 3000);
      }
    },
  },
  watch: {
    query: function (val) {
      if (val.length == 0) {
        this.showSearchModal = false;
      }
    },
  },
};
</script>
