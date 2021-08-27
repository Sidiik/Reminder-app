<template>
  <div class="task">
    <Header />
    <Tasks :tasks="tasks" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Tasks from "./components/Tasks.vue";
export default {
  components: {
    Header,
    Tasks,
  },
  data() {
    return {
      tasks: [],
    };
  },

  created() {
    this.tasks = [
      {
        id: Math.floor(Math.random() * 1000),
        title: "Go to the Mosque",
        day: "30th Aug 2021",
        reminder: true,
      },
      {
        id: Math.floor(Math.random() * 1000),
        title: "Go to the Hospital",
        day: "28th Aug 2021",
        reminder: false,
      },
      {
        id: Math.floor(Math.random() * 1000),
        title: "Update software ",
        day: "10th sept 2021",
        reminder: true,
      },
    ];
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Josefin+Sans&family=PT+Sans&display=swap");

* {
  font-family: "PT Sans", sans-serif;
  padding: 0;
  margin: 0;
}
.task {
  width: 60%;
  margin: auto;
  border: 3px solid rgb(15, 209, 103);
  margin-top: 2rem;
  padding: 2rem;
  border-radius: 0.3rem;
}
.reminder {
  border-left: 7px solid rgb(0, 255, 106);
}
</style>
