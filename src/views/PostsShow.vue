<template>
  <div class="posts-show">
    <h1>id: {{ post.id }}</h1></p>
    <h1>title: {{ post.title }}</h1>
    <h1>body: {{ post.body }}</h1></p>
    <h1>image: {{ post.image}}</h1></p>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios"

export default {
  data: function() {
    return {
      message: "Welcome to the Show",
      post: {}
    };
  },
  created: function() {
    axios.get('/api/posts/' + this.$route.params.id).then(response => {
      console.log(response.data)
      this.post = response.data
    })
  },
  methods: {}
};
</script>
