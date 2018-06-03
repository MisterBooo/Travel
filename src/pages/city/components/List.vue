<template>
    <div class="list" ref="wrapper">
      <div>
         <div class="area">
           <div class="title border-topbottom">当前城市</div>
           <div class="button-list">
             <div class="button-wrapper">
               <div class="button">{{this.$store.state.city}}</div>
             </div>
           </div>
         </div>
        <div class="area">
          <div class="title border-topbottom">热门城市</div>
          <div class="button-list">
            <div class="button-wrapper" v-for="item of hotCities" :key="item.id" @click="handleCityClick(item.name)">
              <div class="button" >{{item.name}}</div>
            </div>
           </div>
        </div>
        <div class="area" v-for="(item,key) of cities" :key="key" :ref="key" >
          <div class="title border-topbottom">{{key}}</div>
          <div class="item-list" v-for="innerItem of item" :key="innerItem.id" >
            <div class="item border-bottom"  :key="innerItem.name"  >{{innerItem.name}}</div>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    cities: Object,
    hotCities: Array,
    letter: String
  },
  methods: {
    handleCityClick (res) {
      alert(res)
      // console.log(city)
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .border-topbottom
    &:before
      border-color : #ccc
    &:after
      border-color : #ccc
  .border-bottom
  &:before
    border-color : #ccc
  .list
    position : absolute
    top: 1.58rem
    left: 0
    right:0
    bottom:0
    overflow : hidden
    .title
      line-height : .54rem
      background: #eee
      padding-left : .2rem
      color : #666
      font-size: .26rem
    .button-list
      padding: .1rem .6rem .1rem .1rem
      overflow : hidden
      .button-wrapper
        float: left
        width: 33.33%
        .button
          padding: .1rem 0
          text-align : center
          margin : .1rem
          border: .02rem solid #ccc
          border-radius : .03rem
    .item-list
      line-height : .54rem
      color: #666
      padding-left: .2rem
</style>
