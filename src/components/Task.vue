<template>
  <div
    :class="[task.reminder ? 'reminder' : '', 'taskItem']"
    @click="toggleReminder"
  >
    <h4>
      {{ task.title }}
    </h4>
    <p>
      {{ task.day }}
    </p>

    <p class="badge bg-primary text-light status">
      -
      {{ this.task.reminder ? "Reminded" : "Not reminded" }}
    </p>
    <span @click="deleteTask(task.id)">&times;</span>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: ["task"],
  methods: {
    deleteTask(id) {
      this.$emit("deleteTask", id);
    },
    toggleReminder() {
      this.task.reminder = !this.task.reminder;
    },
  },
};
</script>

<style scoped>
.taskItem {
  background: #eee;
  padding: 0.3rem 1rem;
  margin-top: 1rem;
  border-radius: 0.2rem;
  cursor: grab;
  position: relative;
  user-select: none;
  transition: all 0.1s ease-in-out;
}
span {
  position: absolute;
  top: 0;
  right: 0;
  padding: 1rem;
  font-size: 31px;
  color: rgb(255, 0, 43);
  cursor: pointer;
}
.status {
  font-weight: 500;
  font-size: 14px;
  /* transition: all 0.3s ease-in-out; */
}
</style>
