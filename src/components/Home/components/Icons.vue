<template>
    <div class="icons">
        <swiper :options="swiperOption">
            <swiper-slide v-for='(page, index) of pages' :key="index">
                <div class="icon" v-for="item of page" :key="item.id">
                    <div class="icon-img" >
                        <img class="icon-img-content" :src="item.imgUrl">
                    </div>
                    <p class="icon-desc">{{item.iconText}}</p>
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>

<script type="text/javascript">
export default {
  name: 'HomeIcon',
  data: function () {
    return {
      swiperOption: {
      },
      iconList: [{
        id: '01',
        imgUrl: require('../../../assets/images/icon1.png'),
        iconText: '景点门票'
      }, {
        id: '02',
        imgUrl: require('../../../assets/images/icon2.png'),
        iconText: '泉城极地'
      }, {
        id: '03',
        imgUrl: require('../../../assets/images/icon3.png'),
        iconText: '一日游'
      }, {
        id: '04',
        imgUrl: require('../../../assets/images/icon4.png'),
        iconText: '欧乐堡'
      }, {
        id: '05',
        imgUrl: require('../../../assets/images/icon5.png'),
        iconText: '台儿庄古城'
      }, {
        id: '06',
        imgUrl: require('../../../assets/images/icon6.png'),
        iconText: '野生动物园'
      }, {
        id: '07',
        imgUrl: require('../../../assets/images/icon7.png'),
        iconText: '故宫'
      }, {
        id: '08',
        imgUrl: require('../../../assets/images/icon8.png'),
        iconText: '每周好货'
      }, {
        id: '09',
        imgUrl: require('../../../assets/images/icon5.png'),
        iconText: '台儿庄古城'
      }, {
        id: '10',
        imgUrl: require('../../../assets/images/icon6.png'),
        iconText: '野生动物园'
      }, {
        id: '11',
        imgUrl: require('../../../assets/images/icon7.png'),
        iconText: '故宫'
      }, {
        id: '12',
        imgUrl: require('../../../assets/images/icon8.png'),
        iconText: '每周好货'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
@import '~styles/mixins.styl'
.icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
.icons
    margin-top: 5px
.icon
    position: relative
    float: left
    width: 25%
    height: 0
    padding-bottom: 25%
    overflow: hidden
.icon-img
    position: absolute
    top: 0
    left: 0
    right: 0
    bottom: 22px
    box-sizing: border-box
    padding: 5px
.icon-desc
    position: absolute
    left: 0
    right: 0
    bottom: 0
    height: 22px
    line-height: 22px
    font-size: 13px
    color: $darkTextColor
    text-align: center
    ellipsis()
.icon-img-content
    display: block
    margin: 0 auto
    height: 100%
</style>
