<template>
  <div :class="[task.reminder ? 'reminder' : '', 'taskItem']">
    <h2>
      {{ task.title }}
    </h2>
    <p>
      {{ task.day }}
    </p>
    <span>&times;</span>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: ["task"],
};
</script>

<style scoped>
.taskItem {
  background: #eee;
  padding: 1rem;
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
