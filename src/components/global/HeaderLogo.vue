<template>
  <div id="site-logo-text">
    <!-- <img
      src="@/assets/logo.png"
      alt="logo"
      class="img-fluid ps-5 pe-5 pt-4 pb-3"
    /> -->
    <span id="inner-text"
      >derek<br /><span style="letter-spacing: -0.15em">w</span
      ><span style="color: #dd3333">.</span
      ><span style="letter-spacing: -0.11em">c</span>o</span
    >
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "HeaderLogo",
});
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Reem+Kufi&display=swap");

#site-logo-text {
  color: #222222;
  margin: 10px;
  font-size: 6em;
  font-weight: 400;
  font-family: "Reem Kufi", "Century Gothic", CenturyGothic, AppleGothic,
    sans-serif;
  line-height: 0.5em;
  text-align: right;
  letter-spacing: -0.08em;
  margin: 20px;
  -webkit-user-select: none; /* Safari */
  -ms-user-select: none; /* IE 10 and IE 11 */
  user-select: none; /* Standard syntax */
}

/* #site-logo-text > span:hover {
  border-bottom: #ffffff solid 3px;
} */
</style>
