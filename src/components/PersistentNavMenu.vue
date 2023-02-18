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
import { Vue } from "vue-class-component";
import NavSidebar from "@/components/NavSidebar.vue";

export default {
  name: "PersistentNavMenu",
  components: {
    NavSidebar,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
