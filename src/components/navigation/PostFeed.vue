<template>
  <div id="post-feed" class="overflow-scroll h-100">
    <ContentLoader
      class="mt-2"
      v-if="Object.keys(this.postList).length === 0"
      msg="Loading posts..."
    />
    <div v-else>
      <ul class="nav nav-pills flex-column mb-auto">
        <li v-for="postId in postIdList" :key="postId.id" class="nav-item">
          <router-link
            :to="{
              path: '/' + this.postList[postId].slug,
            }"
            class="nav-link text-white text-start"
            aria-current="page"
          >
            <div class="post-title">{{ this.postList[postId].title }}</div>
            <div class="post-subtitle">
              {{ this.postList[postId].subtitle }}
            </div>
          </router-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import { defineComponent } from "vue";
import ContentLoader from "@/components/global/ContentLoader.vue";

export default defineComponent({
  name: "PostFeed",

  components: {
    ContentLoader,
  },

  data() {
    return {
      postList: {},
      postIdList: [],
    };
  },

  created: function () {
    this.getPosts();
  },

  methods: {
    getPosts: function () {
      const getPostsURL =
        "https://api.derekw.co/wp-json/wp/v2/posts?per_page=100&orderby=date&order=desc&status=publish&_fields[]=id&_fields[]=slug&_fields[]=title&_fields[]=acf&_fields[]=date&_fields[]=categories";

      const fetchPosts = fetch(getPostsURL)
        .then((response) => response.json())
        .then((data) => {
          return data;
        });

      const processPosts = async () => {
        const res = await fetchPosts;

        for (let i = 0; i < res.length; i++) {
          const postId = res[i]["id"];
          this.postIdList.push(postId);

          const postSlug = res[i]["slug"];
          const postTitle = res[i]["title"]["rendered"];
          const postSubtitle = res[i]["acf"]["subtitle"];
          const postPublished = res[i]["date"];
          const postCategories = res[i]["categories"];

          this.postList[postId] = {};
          this.postList[postId]["id"] = postId;
          this.postList[postId]["slug"] = postSlug;
          this.postList[postId]["title"] = postTitle;
          this.postList[postId]["subtitle"] = postSubtitle;
          this.postList[postId]["published"] = postPublished;
          this.postList[postId]["categories"] = postCategories;
        }
      };

      processPosts();
    },
  },
});
</script>

<style scoped>
.nav-item {
  padding: 5px 20px;
}
#post-feed.list-group-item {
  background-color: none;
}
a.router-link-exact-active {
  background-color: #ffffff17;
}

a:hover {
  background-color: #ffffff08;
}

.post-subtitle {
  font-style: italic;
  font-size: 75%;
  color: #b4b4b4;
}

@media screen and (min-width: 768px) {
  a.router-link-active {
    background-color: #ffffff !important;
    margin-right: -21px !important;
    border-top-right-radius: 0 !important;
    border-bottom-right-radius: 0 !important;
    padding-top: 15px;
    padding-bottom: 15px;
    padding-right: 21px;
  }

  a.router-link-active .post-title,
  a.router-link-active .post-subtitle {
    color: #222222 !important;
  }

  a.router-link-active .post-title {
    font-size: 125%;
    font-weight: 700;
  }
}
</style>
