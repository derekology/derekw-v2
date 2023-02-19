<template>
  <div>
    <p>{{ content }}</p>
  </div>
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
