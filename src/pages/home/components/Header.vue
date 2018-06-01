<template>
 <div class="header">
    <div class="header-left">
       <div class="iconfont back-icon" >&#xe65b;</div>
    </div>
    <div class="header-input">
       <span class="iconfont">&#xe652;</span>
        输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
          {{this.city}}
         <span class="iconfont arrow-icon">&#xe612;</span>
      </div>
    </router-link>
 </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
   .header
     display: flex
     line-height: $headerHeight
     background-color: $bgColor
     color: #fff
     .header-left
       width: .64rem
       float: left
       .back-icon
         text-align: center
         font-size: .4rem
     .header-right
       width: 1.24rem
       float: right
       text-align: center
       color: #ffffff
       .arrow-icon
         font-size: .2rem
     .header-input
       flex: 1
       height: .64rem
       line-height: .64rem
       margin-top: .10rem
       margin-left: .2rem
       padding-left: .2rem
       color: #ccc
       background: #fff
       border-radius: .1rem

</style>
