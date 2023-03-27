<template>
    <div class="header">
        <router-link to="/">
            <div class="iconfont back-icon">&#xe61e;</div>
        </router-link>
        城市选择
    </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header
  position: relative
  height: $header
  line-height: $header
  text-align: center
  color: white
  background-color: $bgColor
  font-size: .32rem
  .back-icon
    position: absolute
    font-size: .4rem
    top: 0
    left: 0
    width: .64rem
    color: white
</style>
