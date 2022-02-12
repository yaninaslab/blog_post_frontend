<template>
  <div>
    <article class="post_card">
      <p>{{ post[1] }}</p>
      <h3>{{ post[2] }}</h3>
      <h6>{{ post[3] }}</h6>
    </article>
  </div>
</template>

<script>
export default {
  name: "blog-post-card",
  props: {
    post: Array,
  },
};
</script>

<style scoped>
.post_card {
  border: 1px solid;
  border-color: grey;
  border-radius: 15px;
  background-color: white;
}
</style>
