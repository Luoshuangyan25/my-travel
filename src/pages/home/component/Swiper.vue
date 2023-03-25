<template>
<div class="wrapper">
    <swiper :options="swiperOption" class="swiper">
        <swiper-slide v-for="item of swiperList" :key="item.id">
            <img class="swiper-img" :src="item.imageUrl">
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '1',
        imageUrl: require('../../../assets/img/1.jpg')
      }, {
        id: '2',
        imageUrl: require('../../../assets/img/2.jpg')
      }, {
        id: '3',
        imageUrl: require('../../../assets/img/3.png')
      }, {
        id: '4',
        imageUrl: require('../../../assets/img/4.png')
      }, {
        id: '5',
        imageUrl: require('../../../assets/img/5.png')
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
  background-color: #fff !important
.wrapper
  overflow: hidden
  width: 100%
  height: 0
  padding-bottom: 35%
  .swiper-img
    width: 100%
</style>
