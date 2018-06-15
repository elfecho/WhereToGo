<template>
  <div id="app">
    <!--keep-alive缓存加载文件-->
    <keep-alive>
      <!--路由就是根据不同的地址，返回不同的内容-->
      <router-view/>
    </keep-alive>
  </div>
</template>

<script>
  export default {
    name: 'App'
  }
</script>

<style>

</style>
