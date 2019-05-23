<template>
    <ul class="list">
        <li
            class="item"
            v-for="item of letters"
            :key="item.initial"
            :ref="item.initial"
            @click="LetterClick"
            @touchstart="touchStart"
            @touchmove="touchMove"
            @touchend="touchEnd"
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
  data: function () {
    return {
      touchStatus: false
    }
  },
  computed: {
    letters () {
      const letters = []
      for (let i = 0; i < this.cities.length; i++) {
        letters.push(this.cities[i])
      }
      return letters
    }
  },
  methods: {
    LetterClick (e) {
      this.$emit('change', e.target.innerText)
    },
    touchStart () {
      this.touchStatus = true
    },
    touchMove (e) {
      if (this.touchStatus) {
        const startY = this.$refs['A'][0].offsetTop
        const touchY = e.touches[0].clientY - 79
        const index = Math.floor((touchY - startY) / 16)
        const number = []
        for (let i = 0; i < this.letters.length; i++) {
          number.push(this.letters[i].initial)
        }
        if (index >= 0 && index < this.letters.length) {
          this.$emit('change', number[index])
        }
      }
    },
    touchEnd () {
      this.touchStatus = false
    }
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
