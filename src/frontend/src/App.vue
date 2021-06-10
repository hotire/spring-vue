<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import request from "request"

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  mounted() {
    request('http://localhost:3000/api/v1/hello', function (error, response, body) {
      window.console.log('error', error)
      window.console.log('response', response && response.statusCode)
      window.console.log('body', body)
    })
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
