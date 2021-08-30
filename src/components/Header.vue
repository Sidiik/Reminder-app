<template>
  <header>
    <h1>Task manager</h1>
    <Button
      @show-hide-task="$emit('show-hide-task')"
      text="Add new item"
      color="#292D3E"
    />
  </header>
</template>

<script>
import Button from "./Button.vue";
export default {
  name: "Header",
  components: { Button },
};
</script>

<style>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
