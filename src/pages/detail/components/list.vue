<template>
    <div>
        <div class="item"
        v-for="(item, index) of list"
        :key="index">
        <div class="item-title border-bottom">
          <img class="item-title-icon" src="~icons/门票.png" alt="">
          {{ item.title }}
        </div>
        <div>
          <!-- 存在children:为多级,把children传入 -->
          <div v-if="item.children" class="item-children">
            <detailList :list="item.children"></detailList>
          </div>
        </div>
      </div>
    </div>
</template>

<script>

export default {
  name: 'detailList',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
.item-title
  line-height: .5rem
  font-size: .32rem
  padding: .2rem
  .item-title-icon
    position: relative
    display: inline-block
    width: .36rem
    height: .36rem
    margin-right: .1rem
    background-size: .4rem .32rem
.item-children
  padding: 0 .3rem
</style>
