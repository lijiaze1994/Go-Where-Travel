<template>
    <div class="header">
        城市选择
        <router-link to='/'>
            <div class="iconfont header-back">&#xe624;</div>
        </router-link>
    </div>
</template>

<script type="text/javascript">
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped="">
@import '~styles/varibles.styl'
.header
    position: relative
    overflow: hidden
    height: 43px
    line-height: 43px
    text-align: center
    color: #fff
    background: $backgroundColor
.header-back
    width: 38px
    text-align: center
    font-size: 20px
    position: absolute
    top: 0
    left: 0
    color: #fff
</style>
