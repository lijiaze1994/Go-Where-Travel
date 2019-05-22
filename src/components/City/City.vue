<template>
    <div>
        <city-header></city-header>
        <city-search></city-search>
        <city-list :hostCities="hostCities" :cities="cities" :letter="letter"></city-list>
        <city-alphabet :cities="cities" @change='LetterChange'></city-alphabet>
    </div>
</template>

<script type="text/javascript">
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import axios from 'axios'
export default {
  name: 'city',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  data: function () {
    return {
      cities: [],
      hostCities: [],
      letter: ''
    }
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json')
        .then(this.getCityInfoSuccess)
    },
    getCityInfoSuccess (res) {
      res = res.data
      if (res.ret && res.city) {
        const data = res.city
        this.cities = data
        this.hostCities = res.hotcity
      }
    },
    LetterChange (letter) {
      this.letter = letter
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>

<style lang="stylus" scoped="">

</style>
