<template>
  <div>
    <nav>
      <div class="navbar navbar-dark bg-dark d-md-none">
        <button
          class="btn btn-primary ms-1 bg-transparent"
          type="button"
          data-bs-toggle="offcanvas"
          data-bs-target="#mob-nav-collapse"
          aria-controls="mob-nav-collapse"
        >
          <menu-icon />
        </button>
        <router-link
          to="/"
          class="nav-link text-white text-start text-center d-md-none"
          aria-current="page"
          ><HeaderLogoHorizontal />
        </router-link>
        <div style="width: 48px"></div>
      </div>
    </nav>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import MenuIcon from "vue-material-design-icons/Menu.vue";
import HeaderLogoHorizontal from "@/components/global/HeaderLogoHorizontal.vue";

export default defineComponent({
  name: "TopNavBar",

  components: {
    MenuIcon,
    HeaderLogoHorizontal,
  },
});
</script>

<style scoped>
.navbar {
  border-top: 5px #dd3333 solid;
  background-color: #222222 !important;
  justify-content: space-between;
  position: fixed;
  width: 100%;
}

.btn {
  /* background-color: #222222; */
  border: 0px;
}

#site-logo-text {
  padding-top: 0px !important;
  padding-bottom: 0px !important;
}
</style>
