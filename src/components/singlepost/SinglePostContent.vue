<template>
  <div id="content">
    <div v-html="content"></div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "SinglePostContent",

  props: {
    content: String,
  },
});
</script>

<style scoped>
/* #content {
  margin: 40px;
  max-width: 900px;
  text-align: left;
} */

img,
svg {
  max-width: 100%;
  height: auto;
  margin-top: 1em;
  margin-bottom: 2em;
}
</style>
