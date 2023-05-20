<script setup>
import MovieList from "./components/MovieList.vue";
</script>

<template>
  <Suspense>
    <div>
      <MovieList />
    </div>
  </Suspense>
</template>

<style scoped>

.MovieList {
  background-color: rgba(0, 0, 0, 0.6);
}

</style>
