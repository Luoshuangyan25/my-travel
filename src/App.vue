<template>
  <div id="app">
    <!-- exclude标记不做keep-alive缓存的组件,Detail页面每次点进要按id发ajax请求/或者用active -->
    <keep-alive exclude="detail">
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
