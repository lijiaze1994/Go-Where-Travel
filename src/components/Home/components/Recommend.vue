<template>
    <div>
        <div class="recommend-title">热门推荐</div>
        <ul>
            <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
                <img class="item-img" :src="item.recommendImg">
                <div class="item-info">
                    <p class="item-title">{{item.itemTitle}}</p>
                    <p class="item-desc">{{item.itemDesc}}</p>
                    <button class="item-button">{{item.button}}</button>
                </div>
            </li>
        </ul>
    </div>
</template>

<script type="text/javascript">
export default {
  name: 'HomeRecommend',
  data: function () {
    return {
      recommendList: [{
        id: '01',
        recommendImg: 'http://img1.qunarzz.com/sight/p0/1902/84/84696f368bbec10da3.img.jpg_200x200_50323152.jpg',
        itemTitle: '北京世界园艺博览会',
        itemDesc: '北京世界园艺博览会北京世界园艺博览会',
        button: '查看详情'
      }, {
        id: '02',
        recommendImg: 'http://img1.qunarzz.com/sight/p0/1708/2b/2b3b94de99c0a425a3.img.jpg_200x200_2458ffb2.jpg',
        itemTitle: '八达岭长城',
        itemDesc: '不到长城非好汉',
        button: '查看详情'
      }, {
        id: '03',
        recommendImg: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
        itemTitle: '故宫',
        itemDesc: '世界五大宫之首，穿越与您近在咫尺',
        button: '查看详情'
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
.item
    overflow: hidden
    display: flex
    height: 120px
.item-img
    width:100px
    height:100px
    padding: 10px
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
    padding: 10px 0
.item-button
    background: #ff9300
    padding: 5px
    border-raduis: 3px
    color: #fff
    margin-top: 6px
    padding: 0 10px
    line-height: 27px
    font-size: 10px
    border: 0
</style>
