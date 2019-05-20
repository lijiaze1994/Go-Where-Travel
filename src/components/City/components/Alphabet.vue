<template>
    <ul class="list">
        <li class="item">A</li>
        <li class="item">A</li>
        <li class="item">A</li>
        <li class="item">A</li>
        <li class="item">A</li>
        <li class="item">A</li>
        <li class="item">A</li>
        <li class="item">A</li>
        <li class="item">A</li>
    </ul>
</template>

<script type="text/javascript">
export default {
  name: 'CityAlphabet'
}
</script>

<style lang="stylus" scoped="">
@import '~styles/varibles.styl'
.list
    position: absolute
    top: 79px
    right: 0
    bottom: 0
    width: 20px
    display: flex
    flex-direction: column
    justify-content: center
.item
    line-height: 20px
    text-align: center
    color: $backgroundColor
    font-size: 14px
</style>
