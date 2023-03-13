<template>
  <div id="sidebar" class="d-flex flex-column flex-shrink-0 text-white">
    <div class="d-md-none offcanvas-header pt-0 pb-0">
      <span class="offcanvas-title mt-1 ms-2" id="sidebar-label"
        >Latest Posts</span
      >
      <button
        type="button"
        class="btn-close text-reset me-2"
        data-bs-dismiss="offcanvas"
        aria-label="close"
      ></button>
    </div>
    <div>
      <router-link
        to="/"
        class="nav-link text-white text-start text-center d-none d-md-block"
        aria-current="page"
        ><HeaderLogoHorizontal />
      </router-link>
      <!-- <span>Latest Posts</span> -->
    </div>

    <PostFeed class="mt-0" />

    <hr class="mb-0" />

    <HorizontalMenu />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import PostFeed from "@/components/navigation/PostFeed.vue";
import HorizontalMenu from "@/components/navigation/HorizontalMenu.vue";
import HeaderLogoHorizontal from "@/components/global/HeaderLogoHorizontal.vue";
// import HeaderLogo from "@/components/global/HeaderLogo.vue";

export default defineComponent({
  name: "NavSidebar",
  components: {
    PostFeed,
    HorizontalMenu,
    HeaderLogoHorizontal,
    // HeaderLogo,
  },

  updated() {
    this.getHeight();
  },

  methods: {
    getHeight: function () {
      let vh = window.innerHeight * 0.01;

      document.documentElement.style.setProperty("--vh", `${vh}px`);
    },
  },
});
</script>

<style scoped>
#sidebar {
  background-color: #222222;
  border-top: 5px #dd3333 solid;
  height: 100vh;
  height: calc(var(--vh, 1vh) * 100);
}
.offcanvas-header .btn-close {
  background-color: #ffffff !important;
  font-size: 75%;
  margin: 10px 5px;
}

#sidebar-label {
  font-size: 20px;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 2px;
}

@media screen and (min-width: 768px) {
  #sidebar {
    width: 230px;
    position: fixed;
    height: 100vh;
  }
}
</style>
