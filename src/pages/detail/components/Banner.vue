<template>
    <div>
        <div class="banner" @click="handleBannerClick">
            <img class="banner-img" :src="bannerImg">
            <div class="banner-info">
                <div class="banner-title">{{sightName}}</div>
                <div class="banner-number">
                    <span class="iconfont banner-icon">&#xe8d3;</span>
                    {{ this.gallaryImgs.length }}
                </div>
            </div>
        </div>
      <CommonPicture
      :imgs="gallaryImgs"
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
      showPicture: false
    }
  },
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
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
