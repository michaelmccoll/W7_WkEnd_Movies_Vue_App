<template>
  <div id="fav_movies">
      <h2 class="fav-title">Favourite Movies</h2>
      <ul>
          <li v-for="favMovie in favMovies"><img class="small-img" :src="favMovie.Poster"/><button class="button" @click="removeFromFavourites(favMovie)">X</button></li>
      </ul>
  </div>
</template>

<script>
export default {
    name: 'fav-movies',
    props: ['favMovies'],
    methods:{
        removeFromFavourites: function(favMovie) {
        this.favMovies.pop(favMovie)
        }
    }
}
</script>

<style>
.small-img {
  height: 100px;
  border: 1px solid;
  border-color: darkgray;
}

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
li {
    display: inline-flex;
    margin: 2px;
    padding: 2px;
}
.button {
    height: 25px;
    width: 25px;
    border-radius: 15px;
    margin: 2px;
    background-color: red;
    color: white;
}
</style>