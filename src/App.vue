<template>
  <div>
    <Header @searching="searchFilm"/>
    <Films :films="films"/>
    <Films :series="series"/>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Films from './components/Films.vue';
import axios from 'axios';
export default {
  components: {
    Header,
    Films
  },
  data() {
    return {
      films: [],
      series:[]
    }
  },
  methods: {
    searchFilm(filmName) {
      axios.get('https://api.themoviedb.org/3/search/movie', {
        params: {
          api_key: 'cb3b792a13241de0d5ed0c7f8a3b9c26',
          language: 'it-IT',
          query: filmName
          
        }
      })
      .then( (response) => {
        this.films = response.data.results;
      });
      axios.get('https://api.themoviedb.org/3/search/tv', {
        params: {
          api_key: 'cb3b792a13241de0d5ed0c7f8a3b9c26',
          language: 'it-IT',
          query: filmName
        }
      })
      .then( (response) => {
        this.series = response.data.results
      });

    }
  }
}
</script>

<style lang="scss">
@import "./assets/style/common";
</style>
         