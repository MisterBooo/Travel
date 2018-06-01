<template>
  <div>
    <div class="search">
      <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音"/>
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li v-for="item of list" :key="item.id" class="search-item border-bottom">{{item.name}}</li>
        <li class="search-item border-bottom" v-show="hasNoData">没有找到匹配数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  watch: {
    keyword () {
      if (this.time) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }

      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 ||
                value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.search)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .search
    height : .72rem
    padding: 0 .1rem
    background : $bgColor
    .search-input
      width: 100%
      box-sizing : border-box
      padding: 0 .1rem
      line-height : .62rem
      text-align : center
      border-radius : .06rem
      color : #666
      height : .62rem
  .search-content
    overflow : hidden
    position : absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    z-index: 1
    background : #eee
    .search-item
      line-height : .62rem
      padding-left : .2rem
      background : #fff
      color: #666

</style>
