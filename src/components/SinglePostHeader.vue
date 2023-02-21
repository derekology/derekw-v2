<template>
  <div>
    <h1>{{ title }}</h1>
    <div>{{ subtitle }}</div>
    <div id="feat_img"><img :src="imageUrl" alt="featured image" /></div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  props: {
    title: String,
    subtitle: String,
    imageUrl: String,
    // yoastData: Object,
  },
})
export default class SinglePostHeader extends Vue {
  title!: string;
  subtitle!: string;
  imageUrl!: string;
  // yoastData!: object;
}
</script>

<style scoped>
#feat_img > img {
  width: 100%;
  height: auto;
}
</style>
