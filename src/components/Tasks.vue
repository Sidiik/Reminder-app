<template>
  <div class="tasks">
    <div v-for="task in tasks" :key="task.id">
      <Task :task="task" />
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
};
</script>

<style>
.tasks {
  margin-top: 2rem;
}
</style>
