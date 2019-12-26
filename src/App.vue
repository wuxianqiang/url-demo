<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
  }
}
</script>

<style>
html, body {
  width: 100%;
  height: 100%;
  padding: 20px;
  box-sizing: border-box;
  font-family: Consolas;
  font-size: 16px;
}
* {
  margin: 0;
  padding: 0;
}
</style>
