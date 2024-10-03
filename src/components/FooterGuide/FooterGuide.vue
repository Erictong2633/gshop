<template>
  <div class="footer_guide">
    <span class="guide_item" :class="{on: '/msite'===$route.path}" @click="goTo('/msite')">
      <span class="item_icon">
        <i class="iconfont icon-waimai"></i>
      </span>
      <span>外卖</span>
    </span>
    <a href="javascript:" class="guide_item" :class="{on: '/search'===$route.path}" @click="goTo('/search')">
      <span class="item_icon">
        <i class="iconfont icon-search"></i>
      </span>
      <span>搜索</span>
    </a>
    <a href="javascript:" class="guide_item" :class="{on: '/order'===$route.path}" @click="goTo('/order')">
      <span class="item_icon">
        <i class="iconfont icon-dingdan"></i>
      </span>
      <span>订单</span>
    </a>
    <a href="javascript:" class="guide_item" :class="{on: '/profile'===$route.path}" @click="goTo('/profile')">
      <span class="item_icon">
        <i class="iconfont icon-geren"></i>
      </span>
      <span>我的</span>
    </a>
  </div>
</template>


<script>
/*
:class是动态绑定元素的class属性,on表示条件判断为true则添加这个类
'/msite'===$route.path表示如何当前路由的路径为msite则结果为true, $route.path表示路由的路径
*/

export default {
  methods: {
    goTo (path) {
      this.$router.replace(path)
    }
  }
}
// 跳转到新页面，不回退旧页面
/*
点击事件在script写一个方法，
this.$router.replace用于替换当前路由,不会留下历史记录。
this.$router.push用于推入新的路由,会保留历史记录。
可以把路由router想象成一个访问记录的栈，router.replace()是替换掉栈顶，而router.push()则是向栈中再堆如一个新记录。
当执行某个操作后需要跳转到一个全新的页面,而不希望通过按钮回到前一个页面时,使用replace；如果希望能够回退到前一个页面，使用push
*/
</script>

<style lang="stylus" rel="stylesheet/stylus">
@import "../../common/stylus/mixins.styl"
.footer_guide  //footer
  top-border-1px(#e4e4e4)
  position fixed
  z-index 100
  left 0
  right 0
  bottom 0
  background-color #fff
  width 100%
  height 50px
  display flex
  .guide_item
    display flex
    flex 1
    text-align center
    flex-direction column
    align-items center
    margin 5px
    color #999999
    &.on
      color #02a774
    span
      font-size 12px
      margin-top 2px
      margin-bottom 2px
      .iconfont
        font-size 22px
</style>
