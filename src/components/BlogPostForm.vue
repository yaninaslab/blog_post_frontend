<template>
  <div>
    <p>{{ message }}</p>
    <br />
    <br />
    <input
      class="posts"
      ref="username_input"
      placeholder="Enter your username"
    />
    <input class="posts" ref="content_input" placeholder="Enter your content" />
    <input
      @click="make_post"
      class="posts_btn"
      type="submit"
      ref="add_post"
      value="Make Post"
    />
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "blog-post-form",
  data() {
    return {
      blog_posts: [],
      message: "",
    };
  },

  methods: {
    make_post() {
      axios
        .request({
          url: "http://yanablogposts.ml//api/blog_post",
          method: "POST",
          data: {
            username: this.$refs.username_input.value,
            content: this.$refs.content_input.value,
          },
        })
        .then(() => {
          this.message = "Post has been successfully added!";
          //   this.blog_posts.push(response.data);
          (this.$refs.username_input.value = ""),
            (this.$refs.content_input.value = "");
        })
        .catch((error) => {
          error.message;
        });
    },
  },
};
</script>

<style scoped>
.posts {
  display: inline-flex;
  margin: 10px;
  width: 300px;
  height: 30px;
  border-radius: 10px;
}
.posts_btn {
  background-color: black;
  color: white;
  font-weight: bolder;
  height: 30px;
  width: 100px;
  margin-left: 10px;
  border-radius: 10px;
}
</style>
