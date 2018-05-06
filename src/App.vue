<template>
  <div id="app">
    <!-- 3.使用组件 -->
    <!-- 第二步：向该组件传递数据（父组件app.vue传递值给子组件Header.vue） -->
    <HeaderView msg="待办事项" />

    <img src="./assets/logo.png">
    <!-- 3.使用组件 -->
    <ListView />
  </div>
</template>

<script>
// 1.倒入组件
// List.vue是App.vue的子组件（App.vue是父组件）
// 父子组件之间的通信问题（组件间通信）
import ListView from './components/List'
import HeaderView from './components/header'

export default {
  name: 'App',
  components: {
    // 2.注册组件
    ListView, HeaderView
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
