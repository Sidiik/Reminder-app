<template>
  <button
    class="btn text-light btnss"
    @click="onClick()"
    :style="{ background: color }"
  >
    {{ text }}
  </button>
</template>

<script>
export default {
  props: ["text", "color"],
  methods: {
    onClick() {
      this.$emit("show-hide-task");
    },
  },
};
</script>

<style>
.btnss {
  border: 0;
  box-shadow: none !important;
}
</style>
