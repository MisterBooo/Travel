<template>
  <div class="wrapper">
    <swiper :options="swiperOption" >
      <swiper-slide v-for="item of swiperList" :key="item.id" >
        <img class="swiper-img" :src="item.imagUrl" />
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imagUrl: 'http://img1.qunarzz.com/piao/fusion/1805/85/ed01cd5307b3f602.jpg_750x200_e54ef754.jpg'
      }, {
        id: '0002',
        imagUrl: 'http://img1.qunarzz.com/piao/fusion/1805/10/3ee6df72beb86402.jpg_750x200_e02a4c99.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background : #fff
  .wrapper
    width : 100%
    height : 0
    overflow : hidden
    padding-bottom : 26.67%
    background : #eee
    .swiper-img
      width : 100%
</style>
