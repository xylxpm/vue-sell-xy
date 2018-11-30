<template>
  <div id="app">
    <vheader :seller="seller"></vheader>
    <div class="tab-wrapper">
      <tab :tabs="tabs"></tab>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  import qs from 'query-string'
  import Vheader from 'components/v-header/v-header'
  import Tab from 'components/tab/tab'
  import { getSeller } from 'api'
  import Goods from 'components/goods/goods'
  import Ratings from 'components/ratings/ratings'
  import Seller from 'components/seller/seller'

  export default {
    name: 'app',
    data() {
      return {
        seller: {

        }
      }
    },
    components: {
      Vheader,
      Tab
    },
    methods: {
      _getSeller() {
        getSeller().then((res) => {
          this.seller = res
        })
      }
    },
    computed: {
      tabs() {
        return [
          {
            label: '商品',
            component: Goods,
            data: {
              seller: this.seller
            }
          },
          {
            label: '评价',
            component: Ratings,
            data: {
              seller: this.seller
            }
          },
          {
            label: '商家',
            component: Seller,
            data: {
              seller: this.seller
            }
          }
        ]
      }
    },
    created() {
      this._getSeller()
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
  #app
    .tab-wrapper
      position: fixed
      top: 135px
      left: 0
      right: 0
      bottom: 0
</style>
