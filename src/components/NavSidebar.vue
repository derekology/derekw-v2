<template>
  <div
    id="sidebar"
    class="d-flex flex-column flex-shrink-0 p-3 text-white vh-100 position-fixed"
  >
    <ul class="nav nav-pills flex-column mb-auto">
      <li class="nav-item mt-2">
        <router-link
          to="/"
          class="nav-link text-white text-start"
          aria-current="page"
        >
          Home
        </router-link>
      </li>
      <li class="nav-item mt-2">
        <router-link to="/about" class="nav-link text-white text-start">
          About
        </router-link>
      </li>
    </ul>
    <hr />

    <PostFeed />

    <hr />
    <div class="dropdown">
      <a
        href="#"
        class="d-flex align-items-center text-white text-decoration-none dropdown-toggle"
        id="dropdownUser1"
        data-bs-toggle="dropdown"
        aria-expanded="false"
      >
        <img
          src="https://github.com/mdo.png"
          alt=""
          class="rounded-circle me-2"
          width="32"
          height="32"
        />
        <strong>mdo</strong>
      </a>
      <ul
        class="dropdown-menu dropdown-menu-dark text-small shadow"
        aria-labelledby="dropdownUser1"
      >
        <li><a class="dropdown-item" href="#">New project...</a></li>
        <li><a class="dropdown-item" href="#">Settings</a></li>
        <li><a class="dropdown-item" href="#">Profile</a></li>
        <li>
          <hr class="dropdown-divider" />
        </li>
        <li><a class="dropdown-item" href="#">Sign out</a></li>
      </ul>
    </div>
  </div>
</template>

<script>
import { Vue } from "vue-class-component";
import PostFeed from "@/components/PostFeed.vue";

export default {
  name: "NavSidebar",
  components: {
    PostFeed,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#sidebar {
  background-color: #222222;
  border-top: 5px #dd3333 solid;
  width: 250px;
}
a.router-link-active {
  background-color: #ffffff17;
}

a:hover {
  background-color: #ffffff08;
}
</style>
