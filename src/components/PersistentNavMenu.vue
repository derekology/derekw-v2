<template>
  <div>
    <div id="sidebar">
      <nav>
        <NavSidebar />
      </nav>
    </div>
  </div>
</template>

<script>
import NavSidebar from "@/components/NavSidebar.vue";

export default {
  name: "PersistentNavMenu",
  components: {
    NavSidebar,
  },
};
</script>

<style scoped></style>
