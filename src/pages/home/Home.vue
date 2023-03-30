<template>
    <div>
        <home-header></home-header>
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
import { mapState } from 'vuex'

export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    Recommend,
    Weekend
  },
  computed: {
    ...mapState({
      city: 'city'
    })
  },
  data () {
    return {
      lastCity: [],
      swiperList: [],
      iconList: [],
      RecommendList: [],
      WeekendList: []
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json?city=' + this.city).then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      let result = res.data
      if (result.ret === true && result.data) {
        this.swiperList = result.data.swiperList
        this.iconList = result.data.iconList
        this.RecommendList = result.data.RecommendList
        this.WeekendList = result.data.WeekendList
      }
    }
  },
  mounted () {
    this.getHomeInfo()
    this.lastCity = this.city
  },
  activated () {
    if (this.lastCity !== this.city) {
      this.lastCity = this.city
      this.getHomeInfo()
    }
  }
}
</script>

<style>
</style>
