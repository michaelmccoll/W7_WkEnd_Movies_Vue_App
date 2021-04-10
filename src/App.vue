<template>
  <div id="app">
    <header>
      <h1>My Movies</h1>
    </header>
    <form v-on:submit.prevent="searchClick()">
      <label for="search"></label>
      <input id="search" type="text" v-model="search" placeholder="Search for a movie...">
      <input type="submit" value="Search">
    </form>
    <movie-detail v-if="movieData" :movieData="movieData"></movie-detail>
    
  </div>
</template>

<script>
import MovieDetail from './components/MovieDetail';
import FavMovie from './components/FavMovie';

export default {
  name: 'App',
  data(){
    return {
      movieData: [],
      favMovies: null,
      search: null,
    } 
  },
  components: {
    'movie-detail': MovieDetail,
    'fav-movie': FavMovie
  },
  mounted(){

  },
  methods:{
    searchClick: function(search){
      fetch(`http://www.omdbapi.com/?t=${this.search}&apikey=2e6f3201`)
        .then(res => res.json())
        .then(data => this.movieData = data)

      // Maybe need to add async - await
  }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
