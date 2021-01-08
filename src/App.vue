<template>
  <div id="app">

 <!-- Router -->
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </div>
  <router-view/>

  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>

a{
color: #fff;
text-decoration:none;
}

</style>




