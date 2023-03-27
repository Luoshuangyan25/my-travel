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
                    <button class="item-button">去看看~</button>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default{
  name: 'Recommend',
  data () {
    return {
      RecommendList: [{
        id: 1,
        imgUrl: 'http://img1.qunarzz.com/sight/p0/2209/59/5984ed6d2d8dae3ea3.water.jpg_600x330_88bd71a5.jpg',
        title: '北京',
        decs: '北京'
      }, {
        id: 2,
        imgUrl: 'http://img1.qunarzz.com/sight/p0/2209/59/5984ed6d2d8dae3ea3.water.jpg_600x330_88bd71a5.jpg',
        title: '北京',
        decs: '北京'
      }, {
        id: 3,
        imgUrl: 'http://img1.qunarzz.com/sight/p0/2209/59/5984ed6d2d8dae3ea3.water.jpg_600x330_88bd71a5.jpg',
        title: '北京',
        decs: '北京'
      }, {
        id: 4,
        imgUrl: 'http://img1.qunarzz.com/sight/p0/2209/59/5984ed6d2d8dae3ea3.water.jpg_600x330_88bd71a5.jpg',
        title: '北京',
        decs: '北京'
      }, {
        id: 5,
        imgUrl: 'http://img1.qunarzz.com/sight/p0/2209/59/5984ed6d2d8dae3ea3.water.jpg_600x330_88bd71a5.jpg',
        title: '北京',
        decs: '北京'
      }]
    }
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
      width: 1.9rem
      height: 1.9rem
      padding: .1rem
    .item-info
      flex: 1
      padding: .1rem
      min-width: 0
    .item-title
      line-height: .54rem
      font-size: .32rem
      ellipsis()
    .item-desc
      line-height: .4rem
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
