<template>
  <div>
    LIKES: <strong>{{likes}}</strong>
    <button
        @click="addLike"
    >LIKE</button>
  </div>
</template>

<script>
export default {
  name: 'App',

  data: () => ({
    likes: 0,
  }),

  methods: {
    addLike() {
      this.likes += 1;
    },
  },

}
</script>

<style scoped>

</style>
