<template>
    <div class="list" ref='wrapper'>
        <div>
            <div class="area">
                <div class="title border-topbottom">当前城市</div>
                <div class="button-list">
                    <div class="button-wrapper">
                        <div class="button">北京</div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom">热门城市</div>
                <div class="button-list">
                    <div class="button-wrapper" v-for="(item, index) of hostCities" :key="index">
                        <div class="button">{{item.name}}</div>
                    </div>
                </div>
            </div>
            <div class="area" v-for="(item, index) of cities" :key="index" :ref="item.initial">
                <div class="title border-topbottom">{{item.initial}}</div>
                <div class="item-list">
                    <div class="item border-bottom" v-for="index of item.list" :key="index.label">{{index.name}}</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script type="text/javascript">
import Bscroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    cities: Array,
    hostCities: Array,
    letter: String
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>

<style lang="stylus" scoped="">
@import '~styles/varibles.styl'
.border-topbottom
    &:before
        border-color: #ccc
    &:after
        border-color: #ccc
.border-topbottom
    &:before
        border-color: #ccc
.list
    overflow: hidden
    position: absolute
    top: 79px
    left: 0
    right: 0
    bottom: 0
.title
    line-height: 25px
    background: #eee
    padding-left: 10px
    color: #666
    font-size: 13px
.button-list
    padding: 5px 30px 5px 5px
    overflow: hidden
.button-wrapper
    width: 33.33%
    float: left
.button
    text-align: center
    margin: 5px
    padding: 5px 0
    border-radius: 3px
    font-size: 14px
    border: 1px solid #ccc
.item-list
    .item
        line-height: 38px
        color: #666
        padding-left: 10px
        font-size: 14px
</style>
