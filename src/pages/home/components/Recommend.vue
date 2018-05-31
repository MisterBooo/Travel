<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" />
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1709/41/411f234d79457081a3.img.jpg_150x150_14d54b9c.jpg',
        title: '长隆野生动物世界',
        desc: '长隆野生动物世界真好玩'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1707/ab/abb70c851caaa6d8a3.img.jpg_150x150_428d0c72.jpg',
        title: '长隆水上乐园',
        desc: '长隆野生动物世界真好玩'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1709/41/411f234d79457081a3.img.jpg_150x150_14d54b9c.jpg',
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
  .item
    display : flex
    overflow : hidden
    height : 1.9rem
    .item-img
      height : 1.7rem
      padding: .1rem
      width : 1.7rem
    .item-info
      flex : 1
      padding: .1rem
      min-width : 0
      .item-title
        line-height : .54rem
        font-size : .32rem
        ellipsis()
      .item-desc
        line-height : .4rem
        color: #ccc
        ellipsis()
      .item-button
        line-height : .44rem
        margin-top : .16rem
        background : #ff9300
        padding : 0 .2rem
        border-radius : .06rem
        color : #fff
</style>
