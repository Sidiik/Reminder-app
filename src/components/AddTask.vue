<template>
  <div class="new-task">
    <h3>New task</h3>
    <form @submit="onSubmit">
      <div class="task-name">
        <input
          type="text"
          v-model="taskName"
          class="form-control"
          placeholder="Task ..."
        />
        <input
          type="date"
          class="form-control mt-2"
          placeholder="Task due ..."
          v-model="due"
        />
      </div>
      <input
        type="checkbox"
        v-model="reminder"
        class="form-control-check mt-2"
        id="check"
      />
      <label for="check"> Show reminder</label>
      <div class="btn w-100">
        <Button text="add new task" color="#7511F7" />
      </div>
    </form>
  </div>
</template>

<script>
import Button from "./Button.vue";
export default {
  name: "AddTask",
  components: {
    Button,
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();
      const newTask = {
        id: Math.floor(Math.random() * 100000),
        title: this.taskName,
        day: this.due,
        reminder: this.reminder,
      };
      this.$emit("add-task", newTask);

      (this.taskName = ""), (this.due = ""), (this.reminder = false);
    },
  },
  emits: ["add-task"],
  data() {
    return {
      taskName: "",
      due: "",
      reminder: false,
    };
  },
};
</script>

<style>
label {
  margin-left: 1rem;
  user-select: none;
  cursor: pointer;
}
</style>
