<template>
  <div
    id="sidebar"
    class="d-flex flex-column flex-shrink-0 text-white vh-100 position-fixed"
  >
    <div>
      <router-link
        to="/"
        class="nav-link text-white text-start text-center d-none d-md-block"
        aria-current="page"
        ><HeaderLogo />
      </router-link>
    </div>

    <PostFeed class="mt-0" />

    <hr class="mb-0" />

    <HorizontalMenu />
  </div>
</template>

<script>
import PostFeed from "@/components/PostFeed.vue";
import HorizontalMenu from "@/components/HorizontalMenu.vue";
import HeaderLogo from "@/components/HeaderLogo.vue";

export default {
  name: "NavSidebar",
  components: {
    PostFeed,
    HorizontalMenu,
    HeaderLogo,
  },
};
</script>

<style scoped>
#sidebar {
  background-color: #222222;
  border-top: 5px #dd3333 solid;
  width: 250px;
}
</style>
