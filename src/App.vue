<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!-- 3.使用组件 -->
    <ListView></ListView>
  </div>
</template>

<script>
// 1.倒入组件
import ListView from './components/List'

export default {
  name: 'App',
  components: {
    // 2.注册组件
    ListView
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
