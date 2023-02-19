<template>
  <div id="post-feed" class="overflow-scroll h-100">
    <!-- <h5>Latest Posts</h5> -->
    <ul class="nav nav-pills flex-column mb-auto">
      <li v-for="post in postList" :key="post.id" class="nav-item">
        <router-link
          :to="{
            path: '/' + post.slug,
          }"
          class="nav-link text-white text-start"
          aria-current="page"
        >
          <div class="post-title">{{ post.title }}</div>
          <!-- <small class="post-subtitle"
            ><em>{{ post.subtitle }}</em></small
          > -->
        </router-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "PostFeed",

  data() {
    return {
      // postList: { 1: { title: "test" } },
      postList: {},
    };
  },

  created: function () {
    this.getPosts();
  },

  methods: {
    getPosts: function () {
      const fetchPosts = fetch(
        "https://derekw.co/wp-json/wp/v2/posts?per_page=100"
      )
        .then((response) => response.json())
        .then((data) => {
          return data;
        });

      const processPosts = async () => {
        const res = await fetchPosts;

        for (let i = 0; i < res.length; i++) {
          const postStatus = res[i]["status"];

          if (postStatus == "publish") {
            const postId = res[i]["id"];

            const postSlug = res[i]["slug"];
            const postTitle = res[i]["title"]["rendered"].replace(
              ' <span class="wp-logo">w!</span>',
              ""
            );
            const postPublished = res[i]["date"];
            const postContent = res[i]["content"]["rendered"];
            const postCategories = res[i]["categories"];

            this.postList[postId] = {};
            this.postList[postId]["id"] = postId;
            this.postList[postId]["slug"] = postSlug;
            this.postList[postId]["title"] = postTitle;
            this.postList[postId]["published"] = postPublished;
            this.postList[postId]["content"] = postContent;
            this.postList[postId]["categories"] = postCategories;
          }
        }
      };

      processPosts();
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.nav-item {
  padding: 5px 20px;
}
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
a.router-link-exact-active {
  background-color: #ffffff17;
}

a:hover {
  background-color: #ffffff08;
}

@media screen and (min-width: 768px) {
  a.router-link-active {
    color: #222222 !important;
    background-color: #ffffff !important;
    margin-right: -21px !important;
    border-top-right-radius: 0 !important;
    border-bottom-right-radius: 0 !important;
    font-weight: 900;
    padding-top: 15px;
    padding-bottom: 15px;
    font-size: 125%;
  }
}
</style>
