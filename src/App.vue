<template>
  <div class="task">
    <Header
      @show-hide-task="showHideTask"
      :buttonText="buttonText"
      :showForm="showForm"
    />
    <AddTask v-if="showForm" @add-task="addTask" />
    <div v-if="tasks.length">
      <Tasks @deleteTask="deleteTask" :tasks="tasks" />
    </div>
    <div v-else>
      <p class="text-danger">No tasks available</p>
    </div>
  </div>
</template>

<script>
import AddTask from "./components/AddTask";
import Header from "./components/Header.vue";
import Tasks from "./components/Tasks.vue";

export default {
  components: {
    Header,
    Tasks,
    AddTask,
  },

  data() {
    return {
      tasks: [],
      showForm: false,
      buttonText: "",
    };
  },

  created() {
    this.tasks = [];
  },
  methods: {
    addTask(task) {
      this.tasks = [...this.tasks, task];
    },
    showHideTask() {
      this.showForm = !this.showForm;
    },
    deleteTask(id) {
      if (confirm("are you sure ? ")) {
        this.tasks = this.tasks.filter((task) => task.id !== id);
      }
    },
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
