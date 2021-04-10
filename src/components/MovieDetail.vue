<template>
<section class="movie-details">
    <h2 v-if="movieData.Title" class="title">{{movieData.Title}}</h2>
    <h3 v-if="movieData.Plot" class="plotT">Description</h3>
    <h4 v-if="movieData.Plot" class="plot">{{movieData.Plot}}</h4>
    <h3 v-if="movieData.Genre" class="genreT">Genre</h3>
    <h4 v-if="movieData.Genre" class="genre">{{movieData.Genre}}</h4>
    <h3 v-if="movieData.Actors" class="actorsT">Actors</h3>
    <h4 v-if="movieData.Actors" class="actors">{{movieData.Actors}}</h4>
    <h3 v-if="movieData.Rated" class="ratedT">Classified</h3>
    <h4 v-if="movieData.Rated" class="rated">{{movieData.Rated}}</h4>
    <h3 v-if="movieData.imdbRating" class="imdbRatingT">Rating</h3>
    <h4 v-if="movieData.imdbRating" class="imdbRating">{{movieData.imdbRating}}</h4>
    <h3 v-if="movieData.Director" class="directorT">Director</h3>
    <h4 v-if="movieData.Director" class="director">{{movieData.Director}}</h4>
    <img v-if="movieData.Poster" class="img" :src="movieData.Poster" alt="">
</section>
</template>

<script>
export default {
    name: "movie-detail",
    props: ["movieData"],
}

</script>

<style>
.title{
    color:rgb(22, 22, 141);
    font-size: 30pt;
    margin: 8px;
    grid-area: title;
}

.plotT{
    margin: 8px;
    color:rgb(22, 22, 141);
    grid-area: plotT;
}
.plot{
    margin: 8px;
    text-align: left;
    grid-area: plot;
}

.genreT{
    margin: 8px;
    color:rgb(22, 22, 141);
    grid-area: genreT;
}
.genre{
    margin: 8px;
    text-align: left;
    grid-area: genre;
}

.actorsT{
    margin: 8px;
    color:rgb(22, 22, 141);
    grid-area: actorsT;
}
.actors{
    margin: 8px;
    text-align: left;
    grid-area: actors;
}

.directorT {
    margin: 8px;
    color:rgb(22, 22, 141);
    grid-area: directorT;
}
.director {
    margin: 8px;
    text-align: left;
    grid-area: director;
}

.ratedT{
    margin: 8px;
    color:rgb(22, 22, 141);
    grid-area: ratedT;
}
.rated{
    margin: 8px;
    text-align: left;
    grid-area: rated;
}

.imdbRatingT{
    margin: 8px;
    color:rgb(22, 22, 141);
    grid-area: imdbRatingT;
}
.imdbRating{
    margin: 8px;
    text-align: left;
    grid-area: imdbRating;
}

.img {
    margin: 8px 8px 8px 80px;
    height: 400px;
    border: 2px solid;
    border-color: darkgray;
    grid-area: image;
}

.movie-details{
    margin: 10px;
    display: grid;
    grid-template-columns: 2fr 1fr 3fr;
    grid-template-rows: auto;
    grid-template-areas:
        "title title title"
        "image plotT plot"
        "image genreT genre"
        "image actorsT actors"
        "image directorT director"
        "image ratedT rated"
        "image imdbRatingT imdbRating"
    ;
}
</style>