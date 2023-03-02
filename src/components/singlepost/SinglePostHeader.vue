<template>
  <div>
    <!-- <main :style="{ 'background-image': `url('${imageUrl})` }"> -->
    <main
      id="post-header"
      :style="{ 'background-image': `url('${imageUrl}')` }"
    >
      <div id="top">
        <div>
          <div id="meta">
            <h1>
              <span id="title">{{ title }}</span>
            </h1>
            <div>{{ subtitle }}</div>
          </div>
        </div>
        <router-link
          to="/"
          class="nav-link text-white text-start text-center d-none d-md-block"
          aria-current="page"
          ><HeaderLogo />
        </router-link>
      </div>
      <!-- <div id="feat_img"><img :src="imageUrl" alt="featured image" /></div> -->
    </main>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import HeaderLogo from "../global/HeaderLogo.vue";

export default defineComponent({
  name: "SinglePostHeader",

  components: {
    HeaderLogo,
  },

  props: {
    title: {
      type: String,
      required: true,
    },
    subtitle: {
      type: String,
      required: true,
    },
    imageUrl: {
      type: String,
      required: true,
    },
    // yoastData: {
    //   type: String,
    //   required: true,
    // },
  },
});
</script>

<style scoped>
#post-header {
  height: 100vh;
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}

/* main > #top {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: #ffffff;
  height: 100%;
  backdrop-filter: brightness(0.4);
} */

#top {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: flex-end;
  text-align: left;
  padding: 40px;
  /* max-width: 900px; */
  margin-right: auto;
  margin-left: auto;
  height: 100%;
}
</style>
