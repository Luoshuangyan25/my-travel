<template>
    <div class="city">
        <city-header></city-header>
        <city-search></city-search>
        <city-list :cities="cities" :hotCities="hotCities" :letter="letter"></city-list>
        <city-alphabet
        :cities="cities"
        @change="handleClick"></city-alphabet>
    </div>
</template>

<script>
import CityHeader from './component/Header.vue'
import CitySearch from './component/Search.vue'
import CityList from './component/List.vue'
import CityAlphabet from './component/Alphabet.vue'
import axios from 'axios'

export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  data () {
    return {
      cities: {},
      hotCities: [],
      letter: ''
    }
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json').then(this.handleGetCityInfo)
    },
    handleGetCityInfo (res) {
      let result = res.data
      if (result.ret && result.data) {
        this.cities = result.data.cities
        this.hotCities = result.data.hotCities
      }
    },
    handleClick (letter) {
      this.letter = letter
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>

<style>
</style>
