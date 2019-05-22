<template>
    <ul class="list">
        <li
            class="item"
            v-for="(item, index) of cities"
            :key="index"
            @click="LetterClick"
        >
            {{item.initial}}
        </li>
    </ul>
</template>

<script type="text/javascript">
export default {
  name: 'CityAlphabet',
  props: {
    cities: Array
  },
  methods: {
    LetterClick (e) {
      this.$emit('change', e.target.innerHTML)
    }
    // TouchStart () {
    //   this.touchStatus = true
    // },
    // TouchMove () {
    //   if (this.touchStatus === true) {
    //   }
    // },
    // TouchEnd () {
    //   this.touchStatus = false
    // }
  }
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
    line-height: 16px
    text-align: center
    color: $backgroundColor
    font-size: 12px
    font-weight:bold
</style>
