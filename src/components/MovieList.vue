<script setup>
import { ref } from "vue";
import axios from "axios";

const APIkey = `e552c8258b3f71b20f3fc069ca964a73`;
const movieData = ref(null);

axios
  .get(
    `https://api.themoviedb.org/3/movie/${movieID}?api_key=${APIkey}&language=en-US`
  )
  .then((movie) => {
    movieData.value = movie.data;
  })
  .catch((error) => {
    console.log("error");
  });

console.log(movieData);
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
    </form>
  </section>
</template>

<style scoped></style>
