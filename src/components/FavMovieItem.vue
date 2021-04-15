<template>
    <li>
      <img class="small-img" :src="favMovie.Poster"/>
    </li>
</template>

<script>
import { eventBus } from '../main';

export default {
    name: 'fav-movie-item',
    props:['favMovie'],
    methods:{
       
    },
}

</script>

<style>
.small-img {
  height: 100px;
  border: 1px solid;
  border-color: darkgray;
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
    background-color:rgb(194, 30, 30);
    color: white;
}
</style>