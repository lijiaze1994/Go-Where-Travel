<template>
    <div>
        <div class="recommend-title">周末去哪儿</div>
        <ul>
            <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
                <div class="item-img-wrapper">
                    <img class="item-img" :src="item.recommendImg">
                </div>
                <div class="item-info">
                    <p class="item-title">{{item.itemTitle}}</p>
                    <p class="item-desc">{{item.itemDesc}}</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script type="text/javascript">
export default {
  name: 'HomeWeekend',
  data: function () {
    return {
      recommendList: [{
        id: '01',
        recommendImg: 'http://img1.qunarzz.com/sight/source/1603/6d/2f67ae0659f41f.jpg_r_640x214_bf6cbd0b.jpg',
        itemTitle: '北京赏花好地方',
        itemDesc: '乱花渐欲迷人眼，京城赏花大搜索'
      }, {
        id: '02',
        recommendImg: 'http://img1.qunarzz.com/sight/source/1811/f3/86173f863bef61.jpg_r_640x214_52b003ac.jpg',
        itemTitle: '京城周末撒欢',
        itemDesc: '在帝都过周末，不仅仅是城中游！'
      }, {
        id: '03',
        recommendImg: 'http://img1.qunarzz.com/sight/source/1811/7e/476589267ebb41.jpg_r_640x214_bf599709.jpg',
        itemTitle: '京城溜娃必去',
        itemDesc: '德智体美劳全面发展的亲子日，这些地方该去看看…'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped="">
.recommend-title
    line-height: 30px
    background: #eee
    text-indent: 10px
    margin-top: 10px
    font-size: 13px
.item-img-wrapper
    height: 0
    overflow: hidden
    padding-bottom: 33.9%
.item-img
    width:100%
.item-info
    flex: 1
    padding: 5px
.item-title
    line-height: 27px
    font-size: .44rem
.item-desc
    line-height: 20px
    font-size: 12px
    color: #ccc
    padding: 2px 0
</style>
