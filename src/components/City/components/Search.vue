<template>
    <div>
        <div class="search">
            <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音" name="">
        </div>
        <div class="search-content" ref="search" v-show="keyword">
            <ul>
                <li class="search-item border-bottom" v-for="item of list" :key="item">{{item}}</li>
                <li class="search-item border-bottom" v-show="hasNoData">没有找到匹配城市</li>
            </ul>
        </div>
    </div>
</template>

<script type="text/javascript">
import Bscroll from 'better-scroll'
export default {
  name: 'CitySearchr',
  props: {
    cities: Array
  },
  data: function () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].list.forEach((value) => {
            if (value.name.indexOf(this.keyword) > -1 || value.pinyin.toLowerCase().indexOf(this.keyword.toLowerCase()) > -1) {
              result.push(value.name)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  }
}
</script>

<style lang="stylus" scoped="">
@import '~styles/varibles.styl'
.search
    height: 36px
    padding: 0 5px
    background: $backgroundColor
.search-input
    width: 100%
    height: 31px
    line-height: 31px
    text-align: center
    border-radius: 3px
    outline: none
    font-size: 14px
    padding: 0 5px
    box-sizing: border-box
.search-content
    overflow: hidden
    position: absolute
    top: 79px
    left: 0
    right: 0
    bottom: 0
    background: #eee
    z-index: 999
.search-item{
    line-height: 28px
    padding-left: 10px
    font-size: 12px
    color: #666
    background: #fff
}
</style>
