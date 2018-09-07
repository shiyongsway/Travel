<template>
  <div id="app">

    <keep-alive exclude="Detail">    <!--路由被加载过一次之后，就把路由的内容放到内存之中，下次进入到这个路由的时候，不需要重新渲染这个组建，从内存中拿出来就好了-->
      <router-view/>   <!--显示的是当前路由地址所对应的内容-->
    </keep-alive>

  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
