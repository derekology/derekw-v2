<template>
  <div id="site-logo-text">
    <!-- <img
          src="@/assets/logo.png"
          alt="logo"
          class="img-fluid ps-5 pe-5 pt-4 pb-3"
        /> -->
    <span id="inner-text">derekw<span style="color: #dd3333">.</span>co</span>
  </div>
</template>

<script>
import { Vue } from "vue-class-component";

export default class HeaderLogo extends Vue {}
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Reem+Kufi&display=swap");

#site-logo-text {
  margin: 10px;
  font-size: 32px;
  text-align: center;
  font-weight: 200;
  font-family: "Reem Kufi", "Century Gothic", CenturyGothic, AppleGothic,
    sans-serif;
}

#site-logo-text > span:hover {
  border-bottom: #ffffff solid 3px;
}
</style>
