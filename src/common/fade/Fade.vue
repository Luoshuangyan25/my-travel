<template>
    <!-- transition增加 渐隐渐现：在元素出现或消失时，过渡效果-->
    <transition>
        <!-- 一个插槽,组件包裹的元素就会被插进来 -->
        <slot></slot>
    </transition>
</template>

<script>
export default {
  name: 'Fade'
}
</script>

<style lang="stylus" scoped>
// 增加 渐隐渐现 样式
.v-enter, .v-leave-to
  opacity: 0
.v-enter-active, .v-leave-active
  transition: opacity .5s
</style>
