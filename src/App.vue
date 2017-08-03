<template>
  <div id="app">
        <router-view></router-view>
        <demo></demo>
  </div>
</template>

<script>
import test from './components/test'
import users from './components/users'
import demo from './components/demo.vue'
export default {
  name: 'app',
  components:{
    test,users,demo
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
