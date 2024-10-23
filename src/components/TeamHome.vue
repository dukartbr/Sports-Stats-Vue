<script setup>
import NewsList from "./NewsList.vue";
import Schedule from "./Schedule.vue";
</script>

<style scoped>
.container {
  width: 100%;
  padding: 0.5rem 0.5rem 0;
  display: flex;
  flex-direction: column;
}

.grow {
  flex-grow: 1;
  display: flex;
}

.teamContent {
  width: 75%;
  display: flex;
  flex-direction: column;
}

.newsCarouselContainer {
  flex: 1;
  padding: 1rem;
  display: flex;
  border-radius: 8px;
}

.newsCarousel {
  background-color: #6faaa0;
  flex: 1;
  border-radius: 8px;
  /* padding: 1rem; */
}

.lowerContent {
  flex: 1;
  display: flex;
}

.lineupContainer {
  width: 100%;
  padding: 1rem 1rem 0;
  display: flex;
}

.lineup {
  width: 100%;
  border-top-right-radius: 8px;
  border-top-left-radius: 8px;
  background-color: #6faaa0;
}
</style>

<template>
  <div class="container">
    <div class="grow">
      <div class="teamContent">
        <div class="newsCarouselContainer">
          <div class="newsCarousel"></div>
        </div>
        <div class="lowerContent">
          <NewsList />
          <div class="lineupContainer">
            <div class="lineup">
              <div class="componentTitle">
                <span class="title">Lineup</span>
              </div>
            </div>
          </div>
        </div>
      </div>
      <Schedule />
    </div>
  </div>
</template>

<script>
export default {};
</script>
