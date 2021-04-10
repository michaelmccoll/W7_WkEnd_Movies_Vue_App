<template>
<section>
  <h2>{{movieData.Title}}</h2>
    <h3>Plot: {{movieData.Plot}}</h3>
    <h3>Director: {{movieData.Director}}</h3>
    <img class="img" :src="movieData.Poster" alt="Movie Poster">
</section>
</template>

<script>
export default {
    name: "movie-detail",
    props: ["movieData"],
}

</script>

<style>
.img {
    height: 400px;
}
</style>