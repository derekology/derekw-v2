<template>
  <div id="content" class="m-auto">
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
#content {
  margin: 40px;
  padding-top: 3em;
  max-width: 740px;
  text-align: left;
  font-size: 18px;
  line-height: 1.8em;
}

img,
svg {
  max-width: 100%;
  height: auto;
  margin-top: 1em;
  margin-bottom: 2em;
}
</style>
