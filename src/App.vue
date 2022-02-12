<template>
  <div id="app">
    <br />
    <br />
    <br />
    <h1>Blog Posts from Users</h1>
    <blog-post-form></blog-post-form>
    <blog-posts></blog-posts>
  </div>
</template>

<script>
import BlogPostForm from "./components/BlogPostForm.vue";
import BlogPosts from "./components/BlogPosts.vue";

export default {
  name: "App",
  components: {
    BlogPostForm,
    BlogPosts,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: whitesmoke;
}
* {
  margin: 0;
  padding: 0;
}
</style>
