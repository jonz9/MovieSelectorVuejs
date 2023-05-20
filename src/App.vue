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
template {
  position: absolute;
  height: 100vh;
  width: 100%;
  overflow: hidden;
}
</style>
