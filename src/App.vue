<template>
  <div class="app">
    <post-form
      @create-post="newPost => posts.push({...newPost})"
    />

    <post-list
      :posts="posts"
    />

  </div>
</template>

<script>
import PostForm from '@/components/PostForm'
import PostList from '@/components/PostList'

export default {
  name: 'App',
  components: {
    PostList,
    PostForm
  },

  data: () => ({
    posts: [
      { id: 1, title: 'JS', body: 'JS Desc' },
      { id: 2, title: 'C#', body: 'C# Desc' },
      { id: 3, title: 'React', body: 'React Desc' },
      { id: 4, title: 'Vue', body: 'Vue Desc' },
      { id: 5, title: 'ASP.NET', body: 'ASP.NET Desc' },
    ],


  }),

  methods: {
  },

}
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  .app {
    padding: 5px 20px;
  }
</style>
