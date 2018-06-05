<template>
    <div>
      <detail-banner></detail-banner>
      <detail-header></detail-header>
      <div class="content">
        <detail-list :list="list"></detail-list>
      </div>
    </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
export default {
  name: 'Detail',
  components: {
    DetailList,
    DetailHeader,
    DetailBanner
  },
  data () {
    return {
      list: [{
        title: '成人票',
        children: [{
          title: '成人联票',
          children: [{
            title: '成人联票---俱乐部'
          }]
        }, {
          title: 'bb'
        }]
      }, {
        title: '学生票'
      }, {
        title: '儿童票'
      }, {
        title: '优惠票'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .content
    height : 50rem
</style>
