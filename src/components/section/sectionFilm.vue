<template>
  <ul>
    <li v-for="film in sharedFilms.films" :key="film.id">
      <h3>{{ film.title }}</h3>
      <h4>{{ film.original_title }}</h4>
      <flag :iso="getFlegs(film.original_language)" />
      <h5>{{ film.vote_average }}</h5>
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
      fleg: "",
    };
  },
  methods: {
    getFlegs(language) {
      return language === "en" ? "gb" : language === "ja" ? "jp" : language;
    },
  },
  created() {
    this.getFlegs(sharedFilms.films);
  },
};
</script>

<style></style>
