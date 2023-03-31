<template>
    <div class="list" ref="wrapper">
        <div>
            <div class="area">
                <div class="title border-top-bottom">当前城市</div>
                <div class="button-list">
                    <div class="button-wrapper">
                        <div class="button">{{this.currentCity}}</div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-top-bottom">热门城市</div>
                <div class="button-list">
                    <div class="button-wrapper" v-for="item of hotCities" :key="item.id" @click="handleCityClick(item.name)">
                        <div class="button">{{item.name}}</div>
                    </div>
                </div>
            </div>
            <div class="area" v-for="(item, key) of cities" :key="key" :ref="key">
                <div class="title border-top-bottom">{{key}}</div>
                <div class="item-list">
                    <div class="item border-bottom"
                    v-for="inner of item"
                    :key="inner.id"
                    @click="handleCityClick(inner.name)">
                    {{inner.name}}</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import BScroll from 'better-scroll' // 使用插件
import { mapState, mapActions } from 'vuex'

export default {
  name: 'CityList',
  methods: {
    handleCityClick (city) {
      // this.$store.dispatch('changeCity', city)
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapActions({
      changeCity: 'changeCity'
    })
  },
  computed: {
    ...mapState({
      currentCity: 'city'
    })
  },
  mounted () {
    this.$nextTick(() => {
      this.scroll = new BScroll(this.$refs.wrapper)
    })
  },
  props: {
    cities: Object,
    hotCities: Array,
    letter: String
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
.border-top-bottom
  &:before
    border-color: #ccc
  &:after
    border-color: #ccc
.border-bottom
  &:before
    border-color: #ccc
.list
  overflow: hidden
  position: absolute
  top: 1.58rem
  left: 0
  right: 0
  bottom: 0
.title
  line-height: .54rem
  background-color: #eee
  padding-left: .2rem
  color: #666
  font-size: .26rem
.button-list
  overflow: hidden
  padding: .1rem .6rem .1rem .1rem
  .button-wrapper
    float: left
    width: 33.33%
    .button
     text-align: center
     padding: .1rem 0
     margin: .1rem
     border: .02rem solid #ccc
     border-radius: .06rem
.item-list
 .item
   line-height: .76rem
   padding-left: .2rem
   color: #666
</style>
