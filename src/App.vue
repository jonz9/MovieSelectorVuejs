<script setup>
import ref from 'vue';
import axios from 'axios';

const APIkey = `e552c8258b3f71b20f3fc069ca964a73`;

axios
.get(url)
.then(async(movieSelected) => {

})



</script>

<template>
  <section id="container">
    <form action="#" id="navbar">
      <label for="select-movies">Select Movies</label>
      <select id="select">
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

    <Suspense>
      <section id="movie-section">
        <img src="" id="poster">
        <div id="movie-info">
          <h1 id="title">{{ title }}</h1>
          <br>
          <h4 id="average-score">{{ average-score }}</h4>
          <h4 id="popularity">{{ popularity }}</h4>
          <h4 id="runtime">{{ runtime }}</h4>
          <h4 id="release-date">{{ release-date }}</h4>
          <h4 id="revenue">{{ revenue }}</h4>
          <h4 id="genres">{{ genres }}</h4>
          <br>
          <p id="overview">{{ overview }}</p>
          <iframe id="trailer" src="" frameborder="0"></iframe>
        </div>
      </section>
    </Suspense>
  </section>
</template>

<style scoped>

</style>