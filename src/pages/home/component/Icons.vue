<template>
    <div class="icons">
      <swiper :options="swiperOption">
        <swiper-slide v-for="(page, index) of pages" :key="index">
            <div class="icon" v-for="item of page" :key="item.id">
              <div class="icon-img">
                  <img class="icon-img-content" :src="item.iconUrl">
              </div>
              <p class="icon-desc">{{item.desc}}</p>
            </div>
        </swiper-slide>
      </swiper>
    </div>
</template>

<script>
export default{
  name: 'HomeIcons',
  data () {
    return {
      swiperOption: {},
      iconList: [{
        id: '1',
        iconUrl: require('icons/门票.png'),
        desc: '景点门票'
      }, {
        id: '2',
        iconUrl: require('icons/温泉.png'),
        desc: '泡温泉'
      }, {
        id: '3',
        iconUrl: require('icons/飞机.png'),
        desc: '航线旅行'
      }, {
        id: '4',
        iconUrl: require('icons/自然风景.png'),
        desc: '自然风景'
      }, {
        id: '5',
        iconUrl: require('icons/美食.png'),
        desc: '美食推荐'
      }, {
        id: '6',
        iconUrl: require('icons/旅游.png'),
        desc: '旅游'
      }, {
        id: '7',
        iconUrl: require('icons/旅游车.png'),
        desc: '观光旅游车'
      }, {
        id: '8',
        iconUrl: require('icons/方向.png'),
        desc: '全国旅游'
      }, {
        id: '9',
        iconUrl: require('icons/名胜古迹.png'),
        desc: '名胜古迹'
      }, {
        id: '10',
        iconUrl: require('icons/地图路线.png'),
        desc: '地图路线'
      }, {
        id: '11',
        iconUrl: require('icons/度假圣地.png'),
        desc: '度假圣地'
      }, {
        id: '12',
        iconUrl: require('icons/缆车.png'),
        desc: '缆车'
      }, {
        id: '13',
        iconUrl: require('icons/美景照片.png'),
        desc: '美景照片'
      }, {
        id: '14',
        iconUrl: require('icons/指南.png'),
        desc: '指南'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const i = Math.floor(index / 8)
        if (!pages[i]) {
          pages[i] = []
        }
        pages[i].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '../../../assets/styles/varibles.styl'
.icons
  margin-top: .1rem
  overflow: hidden
  width: 100%
  height: 0
  padding-bottom: 42%
  .icon
    position relative
    overflow: hidden
    height: 0
    float: left
    width: 25%
    padding-bottom: 20%
    .icon-img
      position: absolute
      top: 0
      left: 0
      right: 0
      bottom: .44rem
      box-sizing: border-box
      padding: .1rem
      .icon-img-content
        display: block
        margin: 0 auto
        height 100%
    .icon-desc
      position: absolute
      left: 0
      right: 0
      bottom: 0
      height: .44rem
      line-height: .44rem
      color: $backColor
      text-align: center
</style>
