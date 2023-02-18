<template>
  <TopNavBar />
  <SlideNavMenu class="bg-transparent" />
  <PersistentNavMenu class="d-none d-md-block" />
  <content class="d-md-flex flex-row">
    <router-view class="m-auto" />
  </content>
</template>

<script lang="ts">
import TopNavBar from "@/components/TopNavBar.vue";
import SlideNavMenu from "@/components/SlideNavMenu.vue";
import PersistentNavMenu from "@/components/PersistentNavMenu.vue";

export default {
  name: "App",
  components: {
    TopNavBar,
    SlideNavMenu,
    PersistentNavMenu,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  box-sizing: border-box;
  overflow-x: hidden;
}

@media screen and (min-width: 768px) {
  content {
    margin-left: 250px;
  }
}
</style>
