<template>
    <div class="search">
        <input class="search-input" type="text" placeholder="输入城市名或拼音" name="">
    </div>
</template>

<script type="text/javascript">
export default {
  name: 'CitySearchr'
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
</style>
