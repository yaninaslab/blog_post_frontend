<template>
  <div>
    <br />
    <br />
    <h1>Blog Posts</h1>
    <p>{{ message }}</p>
    <section class="post_container">
      <article v-for="post in posts" :key="post[0]">
        <blog-post-card :post="post"></blog-post-card>
      </article>
    </section>
  </div>
</template>

<script>
import axios from "axios";
import BlogPostCard from "./BlogPostCard.vue";
export default {
  name: "blog-posts",
  components: {
    BlogPostCard,
  },
  data() {
    return {
      posts: [],
      message: "",
    };
  },
  created() {
    axios
      .request({
        url: "http://yanablogposts.ml//api/blog_post",
        method: "GET",
      })
      .then((res) => {
        console.log(res);
        this.posts = res.data;
      })
      .catch((err) => {
        console.log(err);
        this.message = "Sorry, something went wrong!";
      });
  },
};
</script>

<style scoped>
.post_container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
  margin-top: 30px;
}
</style>
