<template>
  <header>
    <h1>Task manager</h1>
    <Button
      @show-hide-task="$emit('show-hide-task')"
      :text="showForm ? 'Close' : 'Show Form'"
      :color="!showForm ? '#292D3E' : 'rgb(255, 0, 43)'"
    />
  </header>
</template>

<script>
import Button from "./Button.vue";
export default {
  props: ["buttonText", "showForm"],
  name: "Header",
  components: { Button },
  data() {
    return {
      button: !this.showForm,
    };
  },
};
</script>

<style>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
