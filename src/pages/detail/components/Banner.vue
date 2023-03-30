<template>
    <div>
        <div class="banner" @click="handleBannerClick">
            <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1905/29/296e5659470d69bea3.img.jpg_350x240_704ed237.jpg">
            <div class="banner-info">
                <div class="banner-title">长沙世界之窗(AAAA景区)</div>
                <div class="banner-number">
                    <span class="iconfont banner-icon">&#xe8d3;</span>
                    12
                </div>
            </div>
        </div>
      <CommonPicture
      :imgs="imgs"
      v-show="showPicture"
      @close="handleBannerClose"></CommonPicture>
    </div>
</template>

<script>
import CommonPicture from '../../../common/picture/Picture.vue'
export default {
  name: 'detailBanner',
  data () {
    return {
      showPicture: false,
      imgs: ['http://qimgs.qunarzz.com/piao_qsight_provider_piao_qsight_web/0103f120008fwmuiw20FF.jpg_350x240_3850fa2f.jpg']
    }
  },
  components: {
    CommonPicture
  },
  methods: {
    handleBannerClick () {
      this.showPicture = true
    },
    handleBannerClose () {
      this.showPicture = false
    }
  }
}
</script>

<style lang="stylus" scoped>
.banner
  position: relative
  overflow: hidden
  height: 0
  padding-bottom: 54.93%
  .banner-img
    width: 100%
  .banner-info
    display: flex
    position: absolute
    left: 0
    right: 0
    bottom: 0
    line-height: .6rem
    color: #fff
    background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
    .banner-title
      flex: 1
      font-size: .32rem
      padding: 0 .2rem
    .banner-number
      height: .32rem
      line-height: .32rem
      padding: 0 .4rem
      margin-top: .16rem
      border-radius: .2rem
      background-color: rgba(0, 0, 0, .8)
      font-size: .24rem
      .banner-icon
        font-size: .24rem
</style>
