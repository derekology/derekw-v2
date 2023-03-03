<template>
  <div>
    <nav>
      <div class="navbar navbar-dark bg-dark d-md-none">
        <button
          class="btn btn-primary ms-1"
          type="button"
          data-bs-toggle="offcanvas"
          data-bs-target="#mob-nav-collapse"
          aria-controls="mob-nav-collapse"
        >
          <menu-icon />
        </button>
      </div>
    </nav>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import MenuIcon from "vue-material-design-icons/Menu.vue";

export default defineComponent({
  name: "TopNavBar",

  components: {
    MenuIcon,
  },
});
</script>

<style scoped></style>
