<template>
  <div class="posts-new">
    <div class="container">      
      <form v-on:submit.prevent="submit()">
        <h1>Make a new Post</h1>
        <ul>
          <li class="text-danger" v-for="error in errors">{{ error }}</li>
        </ul>
        <div class="form-group">
          <label>Title:</label> 
          <input type="text" class="form-control" v-model="title">
        </div>
        <div class="form-group">
          <label>Body:</label>
          <input type="text" class="form-control" v-model="body">
        </div>
        <div class="form-group">
          <label>User_id:</label>
          <input type="text" class="form-control" v-model="user_id">
        </div>
        <!-- <textarea rows="30" cols="80"></textarea> -->

        <div class="form-group">
          <label>Image :</label>
          <input type="text" class="form-control" v-model="image">
        </div>
        <input type="submit" class="btn btn-primary" value="Submit">
      </form>
    </div>
  </div>
</template>

<script>

import axios from "axios";

export default {
  data: function(){
    return {
      title: "",
      body: "",
      image: "",
      user_id: "",
      errors: []

    };
  },

  methods:{
    submit: function(){
      var params = {
        title: this.title,
        body: this.body,
        image: this.image,
      };
      axios
      .post("/api/posts", params)
      .then(response => {
        this.$router.push("/posts");
      
        })
        .catch(error => {
          this.errors = error.response.data.errors;
      });
    }
  }
};
</script>