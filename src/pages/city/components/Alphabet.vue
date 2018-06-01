<template>
  <div class="list" >
    <div class="item" v-for="(item,key) of cities" :key="key">
      {{key}}
    </div>
  </div>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .list
    display: flex
    flex-direction : column
    justify-content : center
    position : absolute
    right: 0
    top: 1.58rem
    bottom : 0
    width: .4rem
    .item
      text-align : center
      line-height : .4rem
      color: $bgColor
</style>
