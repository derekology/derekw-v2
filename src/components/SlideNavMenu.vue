<template>
  <div>
    <div
      class="offcanvas offcanvas-start bg-transparent"
      tabindex="-1"
      id="sidebar-collapse"
      aria-labelledby="sidebarLabel"
    >
      <div id="sidebar-collapse">
        <nav>
          <NavSidebar />
        </nav>
      </div>
    </div>
  </div>
</template>

<script>
import NavSidebar from "@/components/NavSidebar.vue";

export default {
  name: "SlideNavMenu",

  components: {
    NavSidebar,
  },
};
</script>

<style scoped></style>
