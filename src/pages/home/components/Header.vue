<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont header-back">&#xe617;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe60b;</span>
      输入城市/景点/主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        <!--{{this.this.$store.state.city}}-->
        {{this.city}}
        <span class="iconfont">&#xe601;</span>
      </div>
    </router-link>

  </div>
</template>

<script>
  import { mapState } from 'vuex'
  export default {
    name: "HomeHeader",
    computed: {
      ...mapState(['city'])
    }
  }
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    display: flex
    line-height: .86rem
    background: $bgColor
    color: #fff
    .header-left
      width: .64rem
      float: left
      .header-back
        position: absolute
        top: 0
        left: 0
        width: .64rem
        text-align: center
        font-size: .4rem
        color: #fff
    .header-input
      flex: 1
      height: .64rem
      line-height: .64rem
      margin-top: .12rem
      margin-left: .2rem
      padding-left: .2rem
      background: #fff
      border-radius: .1rem
      color: #ccc
    .header-right
      min-width: 1.04rem
      padding: 0 .1rem
      float: right
      text-align: center
      color: #fff
</style>