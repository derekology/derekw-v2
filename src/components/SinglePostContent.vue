<template>
  <div v-html="content"></div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  props: {
    content: String,
  },
})
export default class SinglePostContent extends Vue {
  content!: string;
}
</script>

<style scoped>
img,
svg {
  max-width: 100% !important;
  height: auto;
}
</style>
