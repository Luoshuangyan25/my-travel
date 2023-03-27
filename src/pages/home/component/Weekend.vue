<template>
    <div class="recommend">
        <div class="title"><img src="~icons/火热推荐.png" class="recommend-icon">热门榜单</div>
        <ul>
            <li class="item" v-for="(item, index) of RecommendList" :key="index">
                <img class="item-img" :src="item.imgUrl">
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.decs}}</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default{
  name: 'Weekend',
  data () {
    return {
      RecommendList: [{
        id: 1,
        imgUrl: 'https://imgs.qunarzz.com/sight/source/1505/91/04b59ae6faf17a.jpg_r_640x214_ce69a65a.jpg',
        title: '北京',
        decs: '北京'
      }, {
        id: 2,
        imgUrl: 'https://imgs.qunarzz.com/sight/source/1505/91/04b59ae6faf17a.jpg_r_640x214_ce69a65a.jpg',
        title: '北京',
        decs: '北京'
      }, {
        id: 3,
        imgUrl: 'https://imgs.qunarzz.com/sight/source/1505/91/04b59ae6faf17a.jpg_r_640x214_ce69a65a.jpg',
        title: '北京',
        decs: '北京'
      }, {
        id: 4,
        imgUrl: 'https://imgs.qunarzz.com/sight/source/1505/91/04b59ae6faf17a.jpg_r_640x214_ce69a65a.jpg',
        title: '北京',
        decs: '北京'
      }, {
        id: 5,
        imgUrl: 'https://imgs.qunarzz.com/sight/source/1505/91/04b59ae6faf17a.jpg_r_640x214_ce69a65a.jpg',
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

  .item-img
    display: block
    width: 100%
    height: auto
    max-width: 100%
  .item-info
    flex: 1
    mix-width: 0
    padding: .1rem
  .item-title
    line-height: .54rem
    font-size: .32rem
    ellipsis()
  .item-desc
    line-height: .4rem
    color: #ccc
    ellipsis()
</style>
