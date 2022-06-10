<template>
  <ul>
    <li v-for="film in sharedFilms.films" :key="film.id">
      {{ film.name }} , {{ film.original_name }} ,
      {{ film.original_language }} , {{ film.vote_average }}
    </li>
  </ul>
</template>

<script>
import sharedFilms from "../shared/sharedFilms";
export default {
  name: "setionTv",
  data() {
    return {
      sharedFilms,
    };
  },
};
</script>

<style></style>
