<script setup>
import MovieList from './components/MovieList.vue';
</script>

<template>
  <Suspense>
    <div>
      <MovieList />
    </div>
  </Suspense>
</template>

<style scoped>
</style>