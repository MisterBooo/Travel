<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="bannerImg"/>
      <div class="banner-info">
        <div class="banner-title">
          {{sightName}}
        </div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe63b;</span>
          99
        </div>
      </div>
    </div>
    <common-gallary :imgs="bannerImgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary
  },
  props: {
    sightName: '',
    bannerImg: '',
    bannerImgs: ''
  },
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1601/3d/3dc7f222d6bca6a790.img.jpg_r_800x800_27e89341.jpg', 'http://img1.qunarzz.com/sight/p0/1601/14/14ada37b4792e56b90.img.jpg_r_800x800_b117e3e5.jpg']
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position: relative
    overflow : hidden
    height : 0
    padding-bottom : 55%
    .banner-img
      width: 100%
    .banner-info
      display : flex
      position absolute
      left:0
      right:0
      bottom:0
      line-height:0.6rem
      color : #fff
      background-image : linear-gradient(top,rgba(0, 0, 0, 0),rgba(0, 0, 0, 0.8))
      .banner-title
        font-size : .32rem
        padding : 0 .2rem
        flex: 1
      .banner-number
        margin-top : .14rem
        padding:0 .4rem 0 .4rem
        font-size : .24rem
        height : .34rem
        line-height : .34rem
        border-radius : .2rem
        background : rgba(0, 0, 0, .8)
        .banner-icon
          font-size : .26rem
</style>
