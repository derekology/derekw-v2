<template>
  <div id="post-feed" class="overflow-scroll h-100">
    <h5>Latest Posts</h5>
    <ul class="nav nav-pills flex-column mb-auto">
      <li class="nav-item mt-2">
        <a href="#" class="nav-link text-white text-start" aria-current="page">
          <div class="post-title">Post Title</div>
          <small class="post-date"><em>Tuesday, Oct 27, 2022</em></small>
        </a>
      </li>
      <li class="nav-item mt-2">
        <a href="#" class="nav-link text-white text-start" aria-current="page">
          <div class="post-title">Post Title</div>
          <small class="post-date"><em>Tuesday, Oct 27, 2022</em></small>
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
import { Vue } from "vue-class-component";

export default class PostFeed extends Vue {}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#post-feed.list-group-item {
  background-color: none;
}
#post-feed::-webkit-scrollbar {
  display: none;
}
#post-feed {
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
}
a.router-link-active {
  background-color: #ffffff17;
}

a:hover {
  background-color: #ffffff08;
}
</style>
