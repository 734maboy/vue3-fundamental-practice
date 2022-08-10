<template>
  <form
      @submit.prevent>
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
</template>

<script>
export default {
  data: () => ({
    postTitle: '',
    postBody: '',
  }),

  methods: {
    createPost() {
      this.$emit('create-post', {
        id: Date.now(),
        title: this.postTitle,
        body: this.postBody
      });
      this.clearForm();
    },

    clearForm() {
      this.postTitle = '';
      this.postBody = '';
    },
  }
}
</script>

<style scoped>
  .input {
    width: 100%;
    border: 1px solid #e34de3;
    padding: 10px;
    margin-top: 10px;
  }

  .btn {
    margin-top: 15px;
    align-self: flex-end;
    padding: 5px 10px;
    background: #8a028a;
    color: white;
    font-weight: 400;
  }

  form {
    display: flex;
    flex-direction: column;
  }
</style>
