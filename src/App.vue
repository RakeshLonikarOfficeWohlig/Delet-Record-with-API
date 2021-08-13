<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <PostComponet /> -->
    <Users />

  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import PostComponet from './components/PostComponet'
import Users from './components/Users.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
    // PostComponet
    Users
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
