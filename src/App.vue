<template>
  <div id="app">
    <router-link to="/hello">跳转第一个页面</router-link> 
    <router-link to="/">跳转第二个页面</router-link>
    <router-view/>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'app',
  computed: mapState({
    // 全局接口请求数据的loading状态
    requestFail: state => state.global.requestFail,
    // 监听接口请求数据的报错状态
    requestLoading: state => state.global.requestLoading
  }),
  watch: {
    requestFail (data) {
      console.log('请求失败了', data)
    }
  }
}
</script>

<style rel="stylesheet/scss" lang="scss">
  @import './styles/index.scss';
body {
  margin: 0;
  padding: 0;
  min-height: 100%;
  min-width: 1000px;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
