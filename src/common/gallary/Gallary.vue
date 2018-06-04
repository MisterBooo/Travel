<template>
    <div class="container" @click="handleGallaryClick">
      <div class="wrapper">
        <swiper :options="swiperOption">
          <swiper-slide v-for="(item, index) in imgs" :key="index">
            <img class="gallary-img" :src="item" />
          </swiper-slide>
        </swiper>
        <div class="swiper-pagination"  slot="pagination"></div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'CommonGallary',
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  methods: {
    handleGallaryClick () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
  .container >>> .swiper-pagination
    overflow : inherit
  .container
    overflow : hidden
    display : flex
    flex-direction : column
    justify-content : center
    z-index : 99
    position: fixed
    right: 0
    top: 0
    background: #000
    left:0
    bottom : 0
    .wrapper
      width : 100%
      height : 0
      padding-bottom : 100%
      .gallary-img
        width: 100%
      .swiper-pagination
        color: #fff
</style>
