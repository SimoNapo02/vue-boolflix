<template>
  <ul>
    <li v-for="film in sharedFilms.films" :key="film.id">
      <img :src="'http://image.tmdb.org/t/p/w342' + film.poster_path" alt="" />
      <h3>{{ film.title }}</h3>
      <h4>{{ film.original_title }}</h4>
      <flag :iso="getFlags(film.original_language)" />
      <h5>{{ film.vote_average }}</h5>
    </li>
  </ul>
</template>

<script>
import sharedFilms from "../shared/sharedFilms";
export default {
  name: "sectionFilm",
  props: {
    films: Array,
    Tv: Array,
  },
  data() {
    return {
      sharedFilms,
      fleg: "",
    };
  },
  methods: {
    getFlags(language) {
      return language === "en" ? "gb" : language === "ja" ? "jp" : language;
    },
  },
};
</script>

<style></style>
