<template>
  <div>
    <nav>
      <div class="navbar navbar-dark bg-dark d-md-none">
        <button
          class="btn btn-primary ms-1"
          type="button"
          data-bs-toggle="offcanvas"
          data-bs-target="#sidebar-collapse"
          aria-controls="sidebar-collapse"
        >
          <span class="glyphicon glyphicon-menu-hamburger">Menu</span>
        </button>
      </div>
    </nav>
  </div>
</template>

<script>
import { Vue } from "vue-class-component";

export default class TopNavBar extends Vue {}
</script>

<style scoped></style>
