<template>
  <div class="city">
    <city-header></city-header>
    <city-search :cities="cities"></city-search>
    <city-list :cities="cities" :hot="hotCities"></city-list>
  </div>
</template>

<script>
  import CityHeader from './components/Header'
  import CitySearch from './components/Search'
  import CityList from './components/List'
  import axios from 'axios'

  export default {
    name: "City",
    components: {
      CityHeader,
      CitySearch,
      CityList
    },
    data() {
      return {
        cities: {},
        hotCities: []
      }
    },
    methods: {
      getCityInfo() {
        axios.get('/api/city.json')
          .then(this.handleGetCityInfoSuccessfully)
      },
      handleGetCityInfoSuccessfully(res) {
        res = res.data
        if (res.ret && res.data) {
          const data = res.data
          this.cities = data.cities
          this.hotCities = data.hotCities
        }
      }
    },
    mounted() {
      this.getCityInfo()
    }
  }
</script>

<style lang="stylus" scoped>

</style>