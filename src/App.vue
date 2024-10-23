<script setup>
import Header from "./components/Header.vue";
import Sidebar from "./components/Sidebar.vue";
import TeamHome from "./components/TeamHome.vue";
</script>

<style scoped>
.body {
  width: 100%;
  display: flex;
}
</style>

<template>
  <Header />
  <div class="body">
    <Sidebar />
    <TeamHome />
  </div>
</template>
