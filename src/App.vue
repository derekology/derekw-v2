<template>
  <TopNavBar />
  <SlideNavMenu />
  <PersistentNavMenu class="d-none d-md-block" />
  <content class="d-md-flex flex-row">
    <router-view class="w-100" />
  </content>
</template>

<script lang="ts">
import { useHead } from "@vueuse/head";
import TopNavBar from "@/components/navigation/TopNavBar.vue";
import SlideNavMenu from "@/components/navigation/SlideNavMenu.vue";
import PersistentNavMenu from "@/components/navigation/PersistentNavMenu.vue";

export default {
  name: "App",
  components: {
    TopNavBar,
    SlideNavMenu,
    PersistentNavMenu,
  },

  setup() {
    useHead({
      title: "Derek Woo",
      meta: [
        {
          name: `robots`,
          content: `noindex`,
        },
        {
          name: `robots`,
          content: `nofollow`,
        },
      ],
    });
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300;0,400;0,500;0,600;0,700;0,800;1,300;1,400;1,500;1,600;1,700;1,800&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,100;0,300;0,400;0,700;0,900;1,100;1,300;1,400;1,700;1,900&display=swap");

#app {
  font-family: "Open Sans", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  box-sizing: border-box;
  overflow-x: hidden;
  font-size: 16px;
}

#content a {
  color: #dd3333 !important;
  text-decoration: none;
}

#content a:hover {
  text-decoration: underline;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: "Lato", Helvetica, Arial, sans-serif;
  font-weight: 700 !important;
  margin-top: 30px !important;
  line-height: 1.5em !important;
}

.wp-block-image {
  text-align: center;
}

#post-feed::-webkit-scrollbar {
  display: none;
}

#post-feed {
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
}

img {
  max-width: 100%;
  height: auto;
  margin: 10px;
}

content {
  margin-top: 60px;
}

/* .offcanvas-backdrop {
  display: none;
} */

@media screen and (min-width: 768px) {
  content {
    margin-left: 230px;
    margin-top: 0px;
  }
}
</style>
