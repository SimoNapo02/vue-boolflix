<template>
  <form @submit.prevent="getFilmAndTv()">
    <input class="input-bar" type="text" placeholder="Cerca" v-model="search" />
    <button type="submit">Search</button>
  </form>
</template>

<script>
import axios from "axios";
import sharedFilms from "../shared/sharedFilms";
export default {
  name: "searchBar",
  data() {
    return {
      search: "",
      sharedFilms,
    };
  },
  methods: {
    getFilmAndTv() {
      axios
        .get("https://api.themoviedb.org/3/search/movie", {
          params: {
            api_key: "5f9cc0198170e2aaf25c4481d2584136",
            query: this.search,
            language: "it-IT",
          },
        })
        .then((response) => {
          sharedFilms.films = response.data.results;
        })
        .catch((error) => {
          console.log(error);
        });
      axios
        .get("https://api.themoviedb.org/3/search/tv", {
          params: {
            api_key: "16322f9823087a057b8e50373be143e8",
            query: this.search,
            language: "it-IT",
          },
        })
        .then((response) => {
          sharedFilms.Tv = response.data.results;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style></style>
