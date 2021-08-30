<template>
  <div :class="[task.reminder ? 'reminder' : '', 'taskItem']">
    <h4>
      {{ task.title }}
    </h4>
    <p>
      {{ task.day }}
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
</style>
