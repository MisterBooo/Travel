<template>
  <div>
    <div class="title">周末去哪儿玩</div>
    <div class="item border-bottom" v-for="item of recommendList" :key="item.id">
      <div class="item-img-wrapper">
        <img class="item-img" :src="item.imgUrl" />
      </div>
      <div class="item-info">
        <p class="item-title">{{item.title}}</p>
        <p class="item-desc">{{item.desc}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/92/580e9ea4f37a1b.jpg_r_640x214_72112761.jpg',
        title: '长隆野生动物世界',
        desc: '长隆野生动物世界真好玩'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/92/580e9ea4f37a1b.jpg_r_640x214_72112761.jpg',
        title: '长隆水上乐园',
        desc: '长隆野生动物世界真好玩'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/92/580e9ea4f37a1b.jpg_r_640x214_72112761.jpg',
        title: '长隆野生动物世界',
        desc: '长隆野生动物世界真好玩'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    line-height : .8rem
    background : #eee
    margin-top .2rem
    text-indent : .2rem
  .item-img-wrapper
    overflow : hidden
    height : 0
    padding-bottom :33.9%
    .item-img
      width : 100%
  .item-info
    padding : 0.1rem
    .item-title
      line-height : .54rem
      font-size : .32rem
      ellipsis()
    .item-desc
      line-height : .4rem
      color: #ccc
      ellipsis()
</style>
