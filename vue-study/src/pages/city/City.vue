<template>
    <div>
        <city-header></city-header>
        <city-search></city-search>
        <city-list :cities="cities" :hot="hot" :letter="letter"></city-list>
        <city-alphabet :cities="cities" @change="handleLetterChange"></city-alphabet>
    </div>
</template>
<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import axios from 'axios';
export default {
  name: 'City',
  components: {
      CityHeader,
      CitySearch,
      CityList,
      CityAlphabet
  },
  data(){
      return{
          cities:{},
          hot:[],
          letter:''
      }
  },
  methods: {
      getCityInfo(){
          axios.get('/api/city.json').then(this.getCityInfoSucc)
      },
      getCityInfoSucc(res){
      res = res.data
      if(res.ret && res.data){
          const data = res.data
          this.cities = data.cities
          this.hot = data.hotCities
      }
    },
    handleLetterChange(letter){
        // console.log(letter)
        this.letter = letter
    }
  },
  mounted () {
      this.getCityInfo()
  }
}
</script>
<style lang="stylus" scoped>
</style>
