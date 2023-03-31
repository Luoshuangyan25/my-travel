<template>
    <div ref="detail">
        <detail-banner :sightName="sightName" :bannerImg="bannerImg" :gallaryImgs="gallaryImgs"></detail-banner>
        <detail-header></detail-header>
        <div class="content">
          <detail-list :list="list"></detail-list>
        </div>
    </div>
</template>

<script>
import detailBanner from './components/Banner.vue'
import detailHeader from './components/Header'
import detailList from './components/list.vue'
import axios from 'axios'

export default {
  name: 'detail',
  components: {
    detailBanner,
    detailHeader,
    detailList
  },
  data () {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      list: []
    }
  },
  methods: {
    getDetailInfo () {
      // 发送ajax请求带上id 写法1,2
      // axios.get('./api/detail.json', {
      //   params: {
      //     id: this.$route.params.id
      //   }
      // })
      axios.get('./api/detail.json?id=' + this.$route.params.id).then(this.handelGetDataSucc)
    },
    handelGetDataSucc (res) {
      let result = res.data
      if (result.ret && result.data) {
        const data = result.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.gallaryImgs = data.gallaryImgs
        this.list = data.categoryList
      }
    }
  },
  mounted () { // 在生命周期钩子,执行发送ajax的函数
    this.getDetailInfo()
  }
}
</script>

<style lang="stylus" scoped>
</style>
