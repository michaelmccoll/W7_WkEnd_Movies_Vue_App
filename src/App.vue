<template>
  <div id="app">
    <header class="header">
      <h1 class="my_movies">My Movies</h1>
      <form v-on:submit.prevent="searchClick()">
        <label for="search"></label>
        <input id="search" type="text" v-model="search" placeholder="Search for a movie...">
        <input type="submit" value="Search">
      </form>
    </header>
    
    <movie-detail v-if="movieData" :movieData="movieData"></movie-detail>

    <button v-if="!favMovies.includes(movieData)" v-on:click="addToFavourites">Add to Favourites</button>

    <fav-movies :favMovies="favMovies"></fav-movies>
 
  </div>
</template>

<script>
import {eventBus} from './main.js'
import MovieDetail from './components/MovieDetail';
import FavMovie from './components/FavMovie.vue';
// import MovieStats from './components/MovieStats.vue';
// import { eventBus } from "@/main.js";

export default {
  name: 'App',
  data(){
    return {
      movieData: [],
      favMovies: [],
      boxOfficeStats: [],
      search: null,
    } 
  },
  components: {
    'movie-detail': MovieDetail,
    'fav-movies': FavMovie,
    // 'movie-stats': MovieStats,
  },
  mounted(){

  },
  methods:{
    searchClick: function(){
      fetch(`http://www.omdbapi.com/?t=${this.search}&apikey=2e6f3201`)
        .then(res => res.json())
        .then(data => this.movieData = data)
    },
    addToFavourites: function() {
      this.favMovies.push(this.movieData)
    },
    },   
}
</script>

<style>
#app {
  font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  text-align: center;
  margin: 5px;
}
.header {
  background-image: url('./assets/movie-header.jpg');
  height: 150px;
  padding: 2px;
}
.my_movies {
  font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 40pt;
  padding: 5px;
  margin: 10px;
  color: white;
}
input {
  margin: 4px;
  padding: 4px;
}
button {
  margin: 8px;
  padding: 4px;
}
</style>
