<template>
  <div class="nav nav-pills flex-row mb-auto row">
    <!-- <div class="nav-item col pe-0">
      <router-link
        to="/"
        class="nav-link text-white text-start text-center"
        aria-current="page"
      >
        Home
      </router-link>
    </div> -->
    <div class="nav-item col ps-0">
      <a
        href="https://me.derekw.co/"
        target="_blank"
        class="nav-link text-white text-starttext-center"
      >
        About / Contact <OpenInNew :size="12" />
      </a>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import OpenInNew from "vue-material-design-icons/OpenInNew.vue";

export default defineComponent({
  name: "HorizontalMenu",

  components: {
    OpenInNew,
  },
});
</script>

<style scoped>
.material-design-icon.icon-2x {
  height: 10px;
  width: 10px;
}

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
