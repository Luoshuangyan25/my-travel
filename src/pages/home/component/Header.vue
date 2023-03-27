<template>
    <div class="header">
        <div class="header-left">
          <div class="iconfont back-icon">&#xe61e;</div>
        </div>
        <div class="iconfont header-input"><span class="search">&#xe632;</span>输入城市/景点/游玩主题</div>
        <div class="iconfont header-right arrow-icon">{{this.city}}&#xe621;</div>
    </div>
</template>

<script>

export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
@import '../../../assets/styles/varibles.styl';
  .header
    display: flex
    line-height: .86rem
    background-color: $bgColor
    color: #fff
    .header-left
      width: .64rem
      float: left
      .back-icon
        text-align: center
        font-size: .4rem
    .header-input
      flex: 1
      height: .64rem
      line-height: .64rem
      margin-top: .12rem
      margin-left: .2rem
      padding-left: .2rem
      background-color: #fff
      border-radius: .1rem
      color: #ccc
      .search
        display: inline-black
        font-size: .35rem
        margin-right: .1rem
    .header-right
      width: 1.24rem
      float: right
      text-align: center
      .arrow-icon
        font-size: .24rem
        margin-left: -.04rem
</style>
