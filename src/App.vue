<template>
  <div>
    <Header @searching="searchFilm"/>
    <div class="container-card">
      <div>
        <Films :films="films" :series="series"/>
      </div>
    </div>
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
      series:[],
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
.container-card{
  height: 100%;
  display: flex;
  justify-content: center;
  flex-direction: column;

  h3{
    margin:40px 0 10px 130px ;
    color: white;
  }
}
</style>
         