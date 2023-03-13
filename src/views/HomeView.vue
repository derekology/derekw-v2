<template>
  <div>
    <main>
      <!-- <div id="logo">
        <HeaderLogo />
      </div> -->
      <div id="title">
        <span id="main-desc">Welcome!</span>
      </div>
      <div id="description">
        <p>
          This personal project is a content-focused front end for derekw.co
          that aims to provide a clean and intuitive user experience. As a very
          early build, you may experience some known bugs, as well as missing
          features. I'm working on them, I promise!
        </p>
        <p>
          To get started, select a content piece
          <span id="desktop">from the sidebar on the right.</span
          ><span id="mobile">in the mobile sidebar.</span>
        </p>
      </div>
    </main>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
// import HeaderLogo from "@/components/global/HeaderLogo.vue";

export default defineComponent({
  name: "HomeView",

  components: {
    // HeaderLogo,
  },
});
</script>

<style scoped>
main {
  /* background-color: #222222; */
  height: 100vh;
  /* border-top: 5px #dd3333 solid; */
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 0px 15%;
}

div#title {
  font-size: 1.75rem;
  font-weight: 400;
  text-align: center;
}

span#main-desc {
  font-weight: 900;
}

div#logo,
div#title,
p#description {
  margin-top: 10px;
  margin-bottom: 10px;
}

#desktop {
  display: none;
}

@media screen and (min-width: 768px) {
  #desktop {
    display: inline;
  }

  #mobile {
    display: none;
  }
}
</style>
