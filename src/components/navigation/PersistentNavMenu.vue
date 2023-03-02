<template>
  <div>
    <div id="sidebar">
      <nav>
        <NavSidebar />
      </nav>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import NavSidebar from "@/components/navigation/NavSidebar.vue";

export default defineComponent({
  name: "PersistentNavMenu",
  components: {
    NavSidebar,
  },
});
</script>

<style scoped></style>
