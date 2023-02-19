<template>
  <div
    id="sidebar"
    class="d-flex flex-column flex-shrink-0 text-white vh-100 position-fixed"
  >
    <PostFeed class="mt-2" />

    <hr class="mb-0" />

    <HorizontalMenu />
  </div>
</template>

<script>
import { Vue } from "vue-class-component";
import PostFeed from "@/components/PostFeed.vue";
import HorizontalMenu from "@/components/HorizontalMenu.vue";

export default {
  name: "NavSidebar",
  components: {
    PostFeed,
    HorizontalMenu,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#sidebar {
  background-color: #222222;
  border-top: 5px #dd3333 solid;
  width: 250px;
}
</style>
