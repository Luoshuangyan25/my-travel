<template>
    <div>
        <home-header :city="city"></home-header>
        <home-swiper :swiperList="swiperList"></home-swiper>
        <home-icons :iconList="iconList"></home-icons>
        <recommend :RecommendList="RecommendList"></recommend>
        <weekend :WeekendList="WeekendList"></weekend>
    </div>
</template>

<script>
import HomeHeader from './component/Header.vue'
import HomeSwiper from './component/Swiper.vue'
import HomeIcons from './component/Icons.vue'
import Recommend from './component/Recommend.vue'
import Weekend from './component/Weekend.vue'
import axios from 'axios'

export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    Recommend,
    Weekend
  },
  data () {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      RecommendList: [],
      WeekendList: []
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json').then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      console.log(res)
      let result = res.data
      if (result.ret === true && result.data) {
        this.city = result.data.city
        this.swiperList = result.data.swiperList
        this.iconList = result.data.iconList
        this.RecommendList = result.data.RecommendList
        this.WeekendList = result.data.WeekendList
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style>
</style>
