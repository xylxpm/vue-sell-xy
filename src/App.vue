<template>
  <div id="app">
    <vheader :seller="seller"></vheader>
  </div>
</template>

<script type="text/ecmascript-6">
  import Vheader from 'components/v-header/v-header'
  import {getSeller} from 'api'

  export default {
    name: 'app',
    data() {
      return {
        seller: {}
      }
    },
    components: {
      Vheader
    },
    methods: {
      _getSeller() {
        getSeller().then((res) => {
          this.seller = res
        })
      }
    },
    created() {
      this._getSeller()
    }
  }
</script>

