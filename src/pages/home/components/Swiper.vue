<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: "HomeSwiper",
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: true,
        speed: 2000,
        loop: true
      },
      swiperList: [{
        id: '001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1805/b6/2330c92270c7e802.jpg_750x200_425e2121.jpg'
      },{
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1806/56/d939255eab633a02.jpg_750x200_c08a2c07.jpg'
      },{
        id: '003',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1806/f0/2a9ec1485adc7302.jpg_750x200_bc4047ed.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff

  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 26%
    .swiper-img
      width: 100%
</style>