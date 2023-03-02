<template>
  <div>{{ msg }}</div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "ContentLoader",

  props: {
    msg: String,
  },
});
</script>

<style scoped>
div {
  font-style: italic;
}
</style>
