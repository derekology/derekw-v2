<template>
  <div>
    <!-- <main :style="{ 'background-image': `url('${imageUrl})` }"> -->
    <main
      id="post-header"
      :style="{
        'background-image': `linear-gradient(to bottom, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.3)),
          url('${imageUrl}')`,
      }"
    >
      <div id="top">
        <div>
          <div id="meta">
            <h1>
              <span id="title">{{ title }}</span>
            </h1>
            <!-- <div>{{ subtitle }}</div> -->
          </div>
        </div>
        <!-- <router-link
          to="/"
          class="nav-link text-white text-start text-center d-none d-md-block"
          aria-current="page"
          ><HeaderLogo />
        </router-link> -->
      </div>
      <!-- <div id="feat_img"><img :src="imageUrl" alt="featured image" /></div> -->
    </main>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
// import HeaderLogo from "../global/HeaderLogo.vue";

export default defineComponent({
  name: "SinglePostHeader",

  components: {
    // HeaderLogo,
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
  background: rgb(0, 0, 0);
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
} */

#top {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: flex-end;
  text-align: center;
  padding: 40px;
  /* max-width: 900px; */
  margin-right: auto;
  margin-left: auto;
  height: 100%;
}

#meta {
  background-color: #000000b6;
  padding: 0px 25px;
}

#top #title {
  color: #ffffff;
  font-size: 6vw;
  text-transform: uppercase;
  letter-spacing: 9px;
  line-height: 2em;
  backdrop-filter: blur(4px);
  -webkit-user-select: none; /* Safari */
  -ms-user-select: none; /* IE 10 and IE 11 */
  user-select: none; /* Standard syntax */
}

@media (min-width: 768px) {
  #top #title {
    font-size: 3vw;
    letter-spacing: 10px;
  }
}
</style>
