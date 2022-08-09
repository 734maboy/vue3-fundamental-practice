<template>
  <div class="app">
    <form>
      <input
          v-model="postTitle"
          class="input"
          type="text"
          placeholder="Post title"
      >
      <input
          v-model="postBody"
          class="input"
          type="text"
          placeholder="Post description"
      >
      <button class="btn" @click="createPost">Create post</button>
    </form>
    <div
        v-for="post in posts"
        :key="`post_ux_${post.id}`"
        class="post">
      <div> <strong>Post title:</strong> {{post.id}}. {{post.title}} </div>
      <div> <strong>Post description:</strong> {{post.body}} </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',

  data: () => ({
    posts: [
      { id: 1, title: 'JS', body: 'JS Desc' },
      { id: 2, title: 'C#', body: 'C# Desc' },
      { id: 3, title: 'React', body: 'React Desc' },
      { id: 4, title: 'Vue', body: 'Vue Desc' },
      { id: 5, title: 'ASP.NET', body: 'ASP.NET Desc' },
    ],

    postTitle: '',
    postBody: '',
  }),

  methods: {
    createPost(e) {
      e.preventDefault();
      this.posts.push({
        id: this.posts.length + 1,
        title: this.postTitle,
        body: this.postBody,
      })
    }
  },

}
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  .post {
    padding: 15px;
    border: 3px solid #e34de3;
    margin: 10px 0;
  }

  .input {
    width: 100%;
    border: 1px solid #e34de3;
    padding: 10px;
    margin-top: 10px;
  }

  form {
    display: flex;
    flex-direction: column;
  }

  .btn {
    margin-top: 15px;
    align-self: flex-end;
    padding: 5px 10px;
    background: #8a028a;
    color: white;
    font-weight: 400;
  }

  .app {
    padding: 5px 20px;
  }
</style>
