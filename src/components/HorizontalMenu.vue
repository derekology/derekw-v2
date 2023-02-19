<template>
  <div class="nav nav-pills flex-row mb-auto row">
    <div class="nav-item col pe-0">
      <router-link
        to="/"
        class="nav-link text-white text-start text-center"
        aria-current="page"
      >
        Home
      </router-link>
    </div>
    <div class="nav-item col ps-0">
      <router-link
        to="/about"
        class="nav-link text-white text-starttext-center"
      >
        About
      </router-link>
    </div>
  </div>
</template>

<script>
import { Vue } from "vue-class-component";

export default {
  name: "HorizontalMenu",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.nav-link {
  border-radius: 0px !important;
}
a.router-link-exact-active {
  background-color: #ffffff17;
}

a:hover {
  background-color: #ffffff08;
}
</style>
