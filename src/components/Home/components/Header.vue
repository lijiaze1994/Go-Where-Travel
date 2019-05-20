<template>
    <div class="header">
        <div class="header-left">
            <div class="iconfont icon-back">&#xe624;</div>
        </div>
        <div class="header-input">
            <span class="iconfont">&#xe632;</span>
            输入城市/景点/游玩主题
        </div>
        <router-link to="/city">
            <div class="header-right">
                {{this.city}}
                <span class="iconfont">&#xe6aa;</span>
            </div>
        </router-link>
    </div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang='stylus' scoped>
@import '~styles/varibles.styl'
.header
    line-height: 43px
    display: flex
    background: $backgroundColor
    color: #fff
.header-left
    width: 38px
    float: left
    text-align: center
.icon-back
    text-align: center
    font-size: 20px
.header-input
    flex: 1
    margin-top: 6px
    height:31px
    line-height: 31px
    font-size: 13px
    margin-left: 2px
    padding-left: 4px
    background: #fff
    border-radius: 5px
    color: #ccc
.header-right
    width: 64px
    float: right
    text-align: center
    font-size: 15px
    color: #fff
</style>
