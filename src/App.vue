<template>
  <div id="app">
    <mt-header fixed title="有盐"></mt-header>
    <router-view></router-view>
    <mt-button type="primary" size="small" @click="test">测试按钮</mt-button>
  </div>
</template>

<script>
export default {
  name: 'app',
  methods: {
    test () {
      this.$http.post('/user/sign')
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
