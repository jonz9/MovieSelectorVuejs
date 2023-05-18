<script setup>
import { ref } from "vue";
import axios from "axios";

const APIkey = `e552c8258b3f71b20f3fc069ca964a73`;
const movieData = ref(false);
const trailerData = ref(false);
const movieID = ref(null);

const getTMDBData = async () => {
  movieData.value = (
    await axios.get(`https://api.themoviedb.org/3/movie/${movieID.value}?api_key=${APIkey}&language=en-US`)
  ).data;

  trailerData.value = (
    await axios.get(
      `https://api.themoviedb.org/3//movie/${movieID.value}/videos?api_key=${APIkey}&language=en-US&adult=false`
    ).results.filter((trailer) => {
      return trailer.type === "Trailer";
    }
    )
  );
};

</script>

<template>
  <section id="container">
    <form action="#" id="navbar">
      <label for="select-movies">Select Movies</label>
      <select v-model="movieID">
        <option value="502356">The Super Mario Bros. Movie</option>
        <option value="677179">Creed III</option>
        <option value="76600">Avatar: The Way of Water</option>
        <option value="638974">Murder Mystery 2</option>
        <option value="594767">Shazam! Fury of the Gods</option>
        <option value="816904">Momias</option>
        <option value="603692">John Wick: Chapter 4</option>
        <option value="758323">The Pope's Exorcist</option>
        <option value="315162">Puss in Boots: The Last Wish</option>
        <option value="842945">Supercell</option>
      </select>
      <button @click="getTMDBData">Get Movie</button>
    </form>

    <section id="movie-section">
      <div v-if="movieData" class="poster">
        <img :src="`https://image.tmdb.org/t/p/w500${movieData.poster_path}`" alt="poster">
      </div>
      <div v-if="movieData" class="movie-info">
        <h1 id="title">{{ movieData.title }}</h1>
        <br>
        <h4 id="average-score">Average Score: {{ movieData.vote_average }}</h4>
        <h4 id="popularity">Popularity: {{ movieData.vote_count }}</h4>
        <h4 id="runtime">Runtime: {{ movieData.runtime }}</h4>
        <h4 id="release-date">Release Date: {{ movieData.release_date }}</h4>
        <h4 id="revenue">Revenue: {{ movieData.revenue }}</h4>
        <h4 id="genres">Genre: {{ movieData.genres[0].name }}</h4>
        <br>
        <p id="overview">Synopsis: {{ movieData.overview }}</p>
        <iframe v-if="trailerData" id="trailer" :src="`https://www.youtube.com/embed/${trailer.at(0).key}`" frameborder="0"></iframe>
      </div>
    </section>
  </section>
</template>
<style scoped>
</style>
