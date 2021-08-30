<template>
  <div class="tasks">
    <div v-for="task in tasks" :key="task.id">
      <Task @deleteTask="deleteTask(task.id)" :task="task" />
    </div>
  </div>
</template>

<script>
import Task from "./Task";
export default {
  components: { Task },
  name: "Tasks",
  props: ["tasks"],
  data() {
    return {};
  },
  methods: {
    deleteTask(id) {
      this.$emit("deleteTask", id);
    },
  },
};
</script>

<style>
.tasks {
  margin-top: 2rem;
}
</style>
