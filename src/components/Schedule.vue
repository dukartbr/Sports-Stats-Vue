<script setup></script>

<style scoped>
.scheduleContainer {
  width: 25%;
  padding: 1rem 1rem 0;
  display: flex;
}

.schedule {
  background-color: #6faaa0;
  flex-grow: 1;
  border-top-right-radius: 8px;
  border-top-left-radius: 8px;
}
</style>

<template>
  <div class="scheduleContainer">
    <div class="schedule">
      <div class="componentTitle">
        <span class="title">This is the schedule</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: [],
  data() {
    return {};
  },
};
</script>
