<template>
  <div>
    <div
      class="offcanvas offcanvas-start bg-transparent"
      data-bs-backdrop="true"
      tabindex="-1"
      id="mob-nav-collapse"
      aria-labelledby="mobNavLabel"
      ref="mobNavCollapse"
    >
      <div>
        <nav>
          <NavSidebar />
        </nav>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import NavSidebar from "@/components/navigation/NavSidebar.vue";

export default defineComponent({
  name: "SlideNavMenu",

  components: {
    NavSidebar,
  },
});
</script>

<style scoped>
/* #sidebar-collapse {
  width: 100%;
} */
</style>
