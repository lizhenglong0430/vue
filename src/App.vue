<template>
  <div id="app">
    <!-- 路由占位符 -->
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: "App",
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
ol,
ul,
li {
  list-style: none;
}
#app{
  width: 100%;
  min-width: 1200px;
  height: 100%;
}
</style>
