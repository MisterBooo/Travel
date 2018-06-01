<template>
    <ul class="list">
      <li class="item">A</li>
      <li class="item">A</li>
      <li class="item">A</li>
      <li class="item">A</li>
      <li class="item">A</li>
      <li class="item">A</li>
    </ul>
</template>

<script>
export default {
  name: 'CityAlphabet'
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
