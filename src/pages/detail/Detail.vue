<template>
    <div>
        <detail-banner></detail-banner>
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

export default {
  name: 'detail',
  components: {
    detailBanner,
    detailHeader,
    detailList
  },
  data () {
    return {
      list: [{
        title: '成人票',
        children: [{
          title: '成人门票',
        }, {
          title: '成人套票',
          children: [{
            title: '25项游乐设施',
          }, {
            title: '50项游乐设施'
          }]
        }]
      }, {
        title: '学生票'
      }, {
        title: '儿童票'
      }, {
        title: '特惠票'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
</style>
