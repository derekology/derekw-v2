<template>
  <div>
    <SinglePostTitle :title="postTitle" />
    <SinglePostContent :content="postContent" />
  </div>
</template>

<script>
import SinglePostTitle from "@/components/SinglePostTitle.vue"; // @ is an alias to /src
import SinglePostContent from "@/components/SinglePostContent.vue"; // @ is an alias to /src

export default {
  name: "PostView",

  components: {
    SinglePostTitle,
    SinglePostContent,
  },

  props: {
    post: {
      type: Object,
      required: true,
    },
  },

  data() {
    return {
      postTitle: this.post.title,
      postContent: this.post.content,
    };
  },
};
</script>
