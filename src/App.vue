<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/Test">About</router-link>  |
      <router-link to="/signup">Signup</router-link> |
      <router-link to="/login">Login</router-link>  |
      <router-link to="/logout">Logout</router-link> |
      <router-link to="/PostsIndex">Posts Index</router-link> |
      <router-link to="/Posts/New">Posts New</router-link> |
      <router-link to="/Posts/Show">Posts Show</router-link> |
    </div>
    <router-view/>
  </div>
</template>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
} */
</style>

// <script>
// export default {
//   methods: {
//     isLoggedIn: function(){
//       console.log(' i am checking if i\ 'm looged in')
//       if (localStorage.getItem("jwt")){
//         return true
//       } else{
//         return false
//       }
//     },
//     getUserId: function (){
//       return parseInt(localStorage.getItem));
//     }
//   }
// }
// </script>
// export default