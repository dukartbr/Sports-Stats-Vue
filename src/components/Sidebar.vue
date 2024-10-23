<script setup></script>

<style scoped>
.sidebar {
  display: flex;
  flex-direction: column;
  background-color: #6faaa0;
  height: calc(100vh - 67.5px);
  width: 15vw;
  text-align: right;
  padding: 1rem 0;
}

.itemsContainer {
  padding: 0.5rem 0;
  display: flex;
  flex-direction: column;
}

.sidebarLink {
  margin: 0.5rem 0;
  padding: 0.5rem 1rem;
}

.sidebarLink:hover {
  background-color: #ff8352;
}

.searchInput {
  background-color: transparent;
  border: 2px solid #000;
  border-radius: 8px;
  padding: 8px;
  margin: 0 0.5rem;
}

.searchInput::placeholder {
  color: #333;
}
</style>

<template>
  <div class="sidebar">
    <input class="searchInput" placeholder="Search a Team..." />
    <div class="itemsContainer">
      <RouterLink
        :to="link.route"
        class="sidebarLink"
        v-for="link in sidebarLinks"
      >
        <span class="title">{{ link.title }}</span>
      </RouterLink>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      sidebarLinks: [
        {
          title: "Team Home",
          route: "/",
        },
        {
          title: "Roster",
          route: "/roster",
        },
      ],
    };
  },
};
</script>
