<template>
  <div class="container">
    <gantt class="left-container" :tasks="tasks"></gantt>
  </div>
</template>

<script>
import Gantt from "./components/Gantt.vue";

export default {
  name: "app",
  components: { Gantt },
  data() {
    return {
      tasks: {
        data: [
          {
            id: 1,
            text: "Task #1",
            start_date: "2020-01-17",
            duration: 8,
            progress: 0.9,
          },
          {
            id: 2,
            text: "Task #2",
            start_date: "2020-01-20",
            duration: 3,
            progress: 0.4,
          },
        ],
        links: [],
      },
    };
  },
};
</script>

<style>
html,
body {
  height: 100%;
  margin: 0;
  padding: 0;
}
.container {
  height: 100%;
  width: 100%;
}
.left-container {
  overflow: hidden;
  position: relative;
  height: 100%;
}
</style>
