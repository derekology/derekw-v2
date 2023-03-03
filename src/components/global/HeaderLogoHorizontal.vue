<template>
  <div id="site-logo-text" class="pt-2 pb-2">
    <span id="inner-text"
      >derek<span style="letter-spacing: -0.08em">w</span
      ><span style="color: #dd3333">.</span
      ><span style="letter-spacing: -0.07em">c</span>o</span
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
  color: #ffffff;
  margin: 10px;
  font-size: 2.5em;
  font-weight: 400;
  font-family: "Reem Kufi", "Century Gothic", CenturyGothic, AppleGothic,
    sans-serif;
  line-height: 0.5em;
  text-align: center;
  letter-spacing: -0.03em;
  margin: 20px;
  -webkit-user-select: none; /* Safari */
  -ms-user-select: none; /* IE 10 and IE 11 */
  user-select: none; /* Standard syntax */
}

/* #site-logo-text > span:hover {
  border-bottom: #ffffff solid 3px;
} */
</style>
