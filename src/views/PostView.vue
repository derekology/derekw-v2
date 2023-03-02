<template>
  <div>
    <main>
      <div id="top">
        <div v-if="this.pageSlug == this.postSlug">
          <SinglePostHeader
            :title="postTitle"
            :subtitle="postSubtitle"
            :imageUrl="postImage"
          />
        </div>
      </div>
      <div id="loader" v-if="this.pageSlug != this.postSlug">
        <HeaderLogo />
        <ContentLoader class="mt-5" msg="Loading content..." />
      </div>
      <SinglePostContent
        v-if="this.pageSlug == this.postSlug"
        :content="postContent"
      />
    </main>
  </div>
</template>

<script>
import { defineComponent } from "vue";
import { useHead } from "@vueuse/head";
import SinglePostHeader from "@/components/singlepost/SinglePostHeader.vue";
import SinglePostContent from "@/components/singlepost/SinglePostContent.vue";
import ContentLoader from "@/components/global/ContentLoader.vue";
import HeaderLogo from "@/components/global/HeaderLogo.vue";

export default defineComponent({
  name: "PostView",

  components: {
    SinglePostHeader,
    SinglePostContent,
    ContentLoader,
    HeaderLogo,
  },

  data() {
    return {
      pageSlug: "",
      postSlug: "",
      postTitle: "",
      postSubtitle: "",
      postContent: "",
      postImage: "",
      postPublished: "",
      postCategories: "",
      yoastData: {},
    };
  },

  setup() {
    useHead({});
  },

  created: function () {
    this.getPost();
  },

  beforeUpdate: function () {
    this.getPost();
  },

  methods: {
    getPageSlug: function () {
      this.pageSlug = window.location.pathname.replace("/", "");
    },

    getPost: function () {
      this.getPageSlug();

      const getPostURL = `https://api.derekw.co/wp-json/wp/v2/posts?per_page=1&slug=${this.pageSlug}&status=publish&_fields[]=yoast_head_json&_fields[]=title&_fields[]=acf&_fields[]=content&_fields[]=date&_fields[]=categories&_fields[]=slug`;

      const fetchPost = fetch(getPostURL)
        .then((response) => response.json())
        .then((data) => {
          return data;
        });

      const parsePost = async () => {
        const res = await fetchPost;

        this.yoastData = JSON.parse(JSON.stringify(res[0]["yoast_head_json"]));
        this.postSlug = res[0]["slug"];

        this.postTitle = res[0]["title"]["rendered"];
        this.postSubtitle = res[0]["acf"]["subtitle"];
        this.postContent = res[0]["content"]["rendered"];
        this.postImage = this.yoastData["og_image"][0]["url"];
        this.postPublished = res[0]["date"];
        this.postCategories = res[0]["categories"];
      };

      parsePost();
    },
  },
});
</script>

<style scoped>
/* main {
  margin: 40px;
  max-width: 900px;
} */

#loader {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding-top: 25vh;
}
</style>
