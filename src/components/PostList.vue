<template>
  <div
      v-for="(post,index) in posts"
      :key="`post_ux_${post.id}`"
      class="post">
    <div> <strong>Post title:</strong> {{index + 1}}. {{post.title}} </div>
    <div> <strong>Post description:</strong> {{post.body}} </div>
  </div>
</template>

<script>
export default {
  name: 'PostList',
  props: {
    posts: {
      type: Array,
      default: () => ([]),
      required: true,
    }
  }
}
</script>

<style scoped>

  .post {
    padding: 15px;
    border: 3px solid #e34de3;
    margin: 10px 0;
  }
</style>
