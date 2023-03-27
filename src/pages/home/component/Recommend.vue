<template>
    <div class="recommend">
        <div class="title"><img src="~icons/火热推荐.png" class="recommend-icon">热门榜单</div>
        <ul>
            <li class="item" v-for="(item, index) of RecommendList" :key="index">
                <div>
                  <img class="item-img" :src="item.imgUrl">
                </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.decs}}</p>
                    <button class="item-button">查看详细</button>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default{
  name: 'Recommend',
  props: {
    RecommendList: Array
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
  .title
    margin-top: .2rem
    line-height: .8rem
    background-color: #f5f5f5
  .recommend-icon
    height: .6rem
    top: 0
    left: 0
    right: 0
    margin-right: .1rem
    box-sizing: border-box
 .item
    overflow: hidden
    display: flex
    width: 100%
    height: 2rem
    .item-img
      width: 2.2rem
      height: 2.2rem
      padding-top: .1rem
    .item-info
      flex: 1
      padding: .1rem
      min-width: 0
      margin-bottom: .5rem
    .item-title
      line-height: .60rem
      font-size: .32rem
      ellipsis()
    .item-desc
      line-height: .4rem
      margin-bottom: .15rem
      color: #ccc
      ellipsis()
    .item-button
      line-height: .44rem
      margin-top: .16rem
      background: #ff9300
      padding: 0 .2rem
      border-radius: .06rem
      color: #fff
</style>
