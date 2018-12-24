<template>
  <div id="app">
    <!-- <test msg="这些是新的属性值！😀"></test> -->
    <users></users>
  </div>
</template>

<script>

import test from './components/Test'
import users from './components/Users'

export default {
  name: 'App',
  components: {
    test,users
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
