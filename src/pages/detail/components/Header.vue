<template>
    <div>
        <router-link
        to="/"
        class="header-abs"
        v-show="showAbs">
            <div class="iconfont back-icon">&#xe61e;</div>
        </router-link>
        <div
        class="header-fixed"
        v-show="!showAbs"
        :style="opacityStyle">
        <!-- 绑定opacityStyle样式：对象 -->
            景点详情
        <router-link to="/">
            <div class="iconfont back-icon-fixed">&#xe61e;</div>
        </router-link>
        </div>
    </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        // 不透明度 0-1之间越小越透明 默认为0
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () { // 滚动事件
    //   console.log(document.documentElement.scrollTop)滑动的距离
      const top = document.documentElement.scrollTop
      if (top > 60) { // 大于60时
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity // 只能是0-1
        this.opacityStyle = {
          opacity: opacity // 更新不透明度
        }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () { // 页面渲染就执行的钩子函数
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () { // 页面即将被隐藏、换成新页面时，就执行的钩子函数
    window.removeEventListener('scroll', this.handleScroll) // 一定要注意移除掉
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
 .header-abs
   position: absolute
   left: .2rem
   top: .2rem
   width: .8rem
   height: .8rem
   border-radius: .4rem
   background: rgba(0, 0, 0, .8)
   text-align: center
   .back-icon
     color: #fff
     font-size: .4rem
     line-height: .8rem
.header-fixed
  position: fixed
  top: 0
  left: 0
  right: 0
  height: $header
  line-height: $header
  text-align: center
  color: white
  background-color: $bgColor
  font-size: .32rem
  .back-icon-fixed
    position: absolute
    font-size: .4rem
    top: 0
    left: 0
    width: .64rem
    color: white
</style>
