
<template>
  <div class="posts - index">
    <h1>{{ message }}</h1>
    Find your Post here: <input type="text" v-model="titleFilter" list="titles">
    <datalist id="titles">
    <option v-for="post in posts">{{post.title}}</option>
    </datalist>
    <div v-for="post in filterBy(posts, titleFilter, 'title', 'body')" v-on:click="currentPost = post" v-bind:class="{selected: currentPost === post}">
    <p>id: {{post.id}}</p>
    <p>title: {{post.title}}</p>
    <p>body : {{post.body}}</p>
    <p>image: {{post.image}}</p>
    <hr>
    </div>
  </div>
</template>

<style>
</style>
<script>
import axios from "axios";
export default {
  data: function() {
    return {
      message: "",
      posts: [],
      titleFilter
    };
  },
  created: function() {
    axios.get('/api/posts').then(response =>{
      console.log(response.data)
      this.posts = response.data
    })
  },
  methods: {}
};
</script>
