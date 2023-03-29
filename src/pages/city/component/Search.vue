<template>
    <div>
        <div class="search">
           <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音">
        </div>
        <div class="search-content" ref="search" v-show="keyword">
            <ul>
                <li class="search-item border-bottom" v-for="item of list" :key="item.id">{{ item.name }}</li>
                <li class="search-item border-bottom" v-show="hasNoData">没有找到这个城市哦~</li>
            </ul>
        </div>
    </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'CitySearch',
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  watch: {
    keyword () {
      if (!this.keyword) {
        this.list = []
        return
      }
      if (this.timer) {
        clearTimeout(this.timer)
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if ((value.spell.indexOf(this.keyword) > -1) || (value.name.indexOf(this.keyword) > -1)) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  props: {
    cities: Object
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.search)
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.search
    height: .72rem
    background-color: $bgColor
    padding: 0 .1rem
    .search-input
        box-sizing: border-box
        width: 100%
        height: .62rem
        line-height: .62rem
        text-align: center
        border-radius: .06rem
        padding: 0 .1rem
        color: #666
.search-content
    position: absolute
    overflow: hidden
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    background-color: #eee
    z-index: 1
    .search-item
      line-height: .62rem
      padding-left: .2rem
      background-color: #fff
      color: #666
</style>
