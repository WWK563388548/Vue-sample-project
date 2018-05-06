<template>
  <div id="app">
    <!-- 3.使用组件 -->
    <!-- 第二步：向该组件传递数据（父组件app.vue传递值给子组件Header.vue） -->
    <HeaderView :msg='title' />

    <img src="./assets/logo.png">
    <!-- 3.使用组件 -->
    <!-- 绑定List.vue中的myInput事件 -->
    <ListView @myInput="getData" />
  </div>
</template>

<script>
// 1.倒入组件
// List.vue是App.vue的子组件（App.vue是父组件）
// 父子组件之间的通信问题（组件间通信）
// 父组件 --> 子组件  使用props选项
// 子组件 --> 父组件  使用自定义事件
import ListView from './components/List'
import HeaderView from './components/header'

export default {
  name: 'App',
  components: {
    // 2.注册组件
    ListView, HeaderView
  },
  data(){
    return {
      title:"待办事项"
    }
  },
  methods: {
    getData(inputMsg){
      // console.log("App.vue: " + inputMsg);
      this.title = "待办事项: " + inputMsg;

    }
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
