<template>
  <div id="app">
    <v-header :seller="seller"></v-header>
    <div class="tab border-1px">
      <div class="tab-item"><router-link to="/goods">商品</router-link></div>
      <div class="tab-item"><router-link to="/ratings">评论</router-link></div>
      <div class="tab-item"><router-link to="/seller">商家</router-link></div>
    </div>
    <keep-alive>
      <router-view :seller="seller"></router-view>
    </keep-alive>
  </div>
</template>

<script>
import Header from './components/header/header'
import axios from 'axios'
import {urlParse} from './common/js/util'

const ERR_OK = 0

export default {
  name: 'app',
  data () {
    return {
      seller: {
        id: (() => {
          let queryParam = urlParse()
          return queryParam.id
        })()
      }
    }
  },
  created () {
    axios.get('/api/seller?id=' + this.seller.id)
    .then((res) => {
      let v = res.data
      if (v.errno === ERR_OK) {
        /**
         * Object.assign: 函数参数为一个目标对象（该对象作为最终的返回值）,源对象(此处可以为任意多个)。通过调用该函数可以拷贝所有可被枚举的自有属性值到目标对象中。
         * http://cnodejs.org/topic/56c49662db16d3343df34b13
         */
        this.seller = Object.assign({}, this.seller, v.data)
      }
    })
  },
  components: {
    'v-header': Header
  }
}
</script>

<style lang="stylus">
@import "./common/styles/mixin.styl"

#app
  .tab
    display: flex
    width: 100%
    height: 40px
    line-height: 40px
    border-top-1px(rgba(7,17,27,0.1))
    border-bottom-1px(rgba(7,17,27,0.1))
    .tab-item
      flex: 1
      text-align: center
      & > a
        display: block
        font-size: 14px
        color: rgb(77,85,93)
        &.router-link-active
          color: rgb(240,20,20)
</style>
