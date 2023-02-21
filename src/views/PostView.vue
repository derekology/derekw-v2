<template>
  <div>
    <LoadingContent
      class="mt-4"
      v-if="this.pageSlug != this.postSlug"
      msg="Loading content..."
    />
    <div v-else>
      <SinglePostHeader
        :title="postTitle"
        :subtitle="postSubtitle"
        :imageUrl="postImage"
      />
      <SinglePostContent :content="postContent" />
    </div>
  </div>
</template>

<script>
import SinglePostHeader from "@/components/SinglePostHeader.vue";
import SinglePostContent from "@/components/SinglePostContent.vue";
import LoadingContent from "@/components/LoadingContent.vue";

export default {
  name: "PostView",

  components: {
    SinglePostHeader,
    SinglePostContent,
    LoadingContent,
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

  beforeMount: function () {
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
};
</script>
