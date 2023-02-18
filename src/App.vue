<template>
  <TopNavBar />
  <SlideNavMenu class="bg-transparent" />
  <content class="row">
    <PersistentNavMenu class="col-3 d-none d-md-block" />
    <router-view class="col" />
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
}
nav a {
  font-weight: bold;
  color: #2c3e50;
}
nav a.router-link-exact-active {
  color: #42b983;
}
</style>
