<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">主页</router-link> |
      <router-link to="/about">更多</router-link> |
      <router-link to="/test">测试</router-link> |
      <router-link to="/ele">表格</router-link> |
    </div>
    <div id="main">

    <router-view />
    </div>
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  height:80px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
#main{
  // height:calc(100vh - 80px);
  background:skyblue;
  padding:20px;
}
</style>
