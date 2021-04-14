<template>
  <div id="fav_movies">
      <h2 class="fav-title">Favourite Movies</h2>
      <ul>
          <fav-movie-item v-for="(favMovie, index) in favMovies" :key="index" :favMovie="favMovie">
          </fav-movie-item>
      </ul>
  </div>
</template>

<script>

import FavMovieItem from './FavMovieItem.vue'

export default {
    name: 'fav-movies',
    props: ['favMovies'],
    components: {
        'fav-movie-item': FavMovieItem,
    },
    methods:{

    }

}

</script>

<style>
.fav-title{
    padding: 8px 4px;
    margin: 4px;
    color: white;
    background-color: rgb(194, 30, 30);
}
ul {
    padding: 4px;
    margin: 4px 4px 18px 4px;
}

</style>