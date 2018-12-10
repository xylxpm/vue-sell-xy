<template>
  <cube-scroll class="seller">
    <div class="seller-content">
      <div class="overview">
        <h1 class="title"></h1>
        <div class="desc border-bottom-1px">
          <star :size="36"></star>
          <span class="text">内容</span>
          <span class="text">月售</span>
        </div>
        <ul class="remark">
          <li class="block">
            <h2>起送价</h2>
            <div class="content">
              <span class="stress">价格</span>元
            </div>
          </li>
          <li class="block">
            <h2>商家配送</h2>
            <div class="content">
              <span class="stress">价格</span>元
            </div>
          </li>
          <li class="block">
            <h2>平均配送时间</h2>
            <div class="content">
              <span class="stress">价格</span>分钟
            </div>
          </li>
        </ul>
        <div class="favorite">
          <span class="icon--favorite"></span>
          <span class="text"></span>
        </div>
      </div>
      <split></split>
      <div class="bulletin">
        <h1 class="title">公告与活动</h1>
        <div class="content-wrapper border-bottom-1px">
          <p class="content">bulletin</p>
        </div>
        <ul class="supports">
          <li class="support-item border-bottom-1px">
            <support-ico :size="4"></support-ico>
            <span class="text">内容</span>
          </li>
        </ul>
      </div>
      <split></split>
      <div class="pics">
        <h1 class="title">商家实景</h1>
        <cube-scroll class="pic-wrapper">
          <ul class="pic-list">
            <li class="pic-item">
              <img width="120" height="90" src=""/>
            </li>
          </ul>
        </cube-scroll>
      </div>
      <split></split>
      <div class="info">
        <h1 class="title border-bottom-1px">商家信息</h1>
        <ul>
          <li class="info-item border-bottom-1px">
            信息
          </li>
        </ul>
      </div>
    </div>
  </cube-scroll>
</template>

<script type="text/ecmascript-6">
  import Split from 'components/split/split'
  import Star from 'components/star/star'
  import SupportIco from 'components/support-ico/support-ico'

  export default {
    name: 'seller',
    components: {
      Split,
      Star,
      SupportIco
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  @import "~common/stylus/variable"
  @import "~common/stylus/mixin"

  .seller
    height: 100%
    text-align: left
    .overview
      position: relative
      padding: 18px
      .title
        margin-bottom: 8px
        line-height: 14px
        font-size: $fontsize-medium
        color: $color-dark-grey
      .desc
        display: flex
        align-items: center
        padding-bottom: 18px
        .star
          margin-right: 8px
        .text
          margin-right: 12px
          line-height: 18px
          font-size: $fontsize-small-s
          color: $color-grey

      .remark
        display: flex
        padding-top: 18px
        .block
          flex: 1
          text-align: center
          border-right: 1px solid $color-col-line
          &:last-clild
            border: none
          h2
            margin-bottom :4px
            line-height :10px
            font-size:$fontsize-small-s
            color:$color-light-grey
          .content
            line-height :24px
            font-size:$fontsize-small-s
            color:$color-dark-grey
            .stress
              font-size:$fontsize-large-xxx


    .bulletin
      padding: 18px 18px 0 18px
      white-space: normal
    .pics
      padding: 18px
    .info
      padding: 18px 18px 0 18px
      color: $color-dark-grey

</style>
