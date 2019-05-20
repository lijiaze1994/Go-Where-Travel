<template>
    <div class="wrapper">
        <swiper :options="swiperOption" v-if='showSwiper'>
        <!-- slides -->
        <swiper-slide v-for="item of list" v-bind:key="item.id">
            <img class="swiper-img" v-bind:src='item.imgUrl' />
        </swiper-slide>
     <!--    <swiper-slide>
            <img class="swiper-img" src="~images/swiper2.jpg" />
        </swiper-slide>
        <swiper-slide>
            <img class="swiper-img" src="~images/swiper3.jpg" />
        </swiper-slide>
        <swiper-slide>
            <img class="swiper-img" src="~images/swiper4.jpg" />
        </swiper-slide> -->
        <!-- Optional controls -->
        <div class="swiper-pagination"  slot="pagination"></div>
      <!--   <div class="swiper-button-prev" slot="button-prev"></div>
        <div class="swiper-button-next" slot="button-next"></div> -->
     <!--    <div class="swiper-scrollbar"   slot="scrollbar"></div> -->
      </swiper>
    </div>
</template>
<script type="text/javascript">
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  computed: {
    showSwiper () {
      return this.list.length
    }
  },
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        speed: 1500
      },
      swiperList: [{
        id: '01',
        imgUrl: require('../../../assets/images/swiper.jpg')
      }, {
        id: '02',
        imgUrl: require('../../../assets/images/swiper2.jpg')
      }, {
        id: '03',
        imgUrl: require('../../../assets/images/swiper3.jpg')
      }, {
        id: '04',
        imgUrl: require('../../../assets/images/swiper4.jpg')
      }]
    }
  }
}
</script>
<style lang='stylus' scoped>
.wrapper
    width: 100%
    height: 0
    overflow: hidden
    padding-bottom: 26.7%
.swiper-img
    width: 100%
.wrapper >>> .swiper-pagination-bullet-active
    background: #fff
</style>
