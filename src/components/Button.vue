<template>
  <button class="btn text-light" :style="{ background: color }">
    {{ text }}
  </button>
</template>

<script>
export default {
  props: ["text", "color"],
};
</script>

<style></style>
