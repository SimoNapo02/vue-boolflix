<template>
  <ul>
    <li v-for="film in sharedFilms.films" :key="film.id">
      {{ film.title }} , {{ film.original_title }} ,
      {{ film.original_language }} , {{ film.vote_average }}
    </li>
  </ul>
</template>

<script>
import sharedFilms from "../shared/sharedFilms";
export default {
  name: "sectionFilm",
  data() {
    return {
      sharedFilms,
    };
  },
};
</script>

<style></style>
