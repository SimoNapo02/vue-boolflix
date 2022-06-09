<template>
  <header>
    <SearchBar />
  </header>
</template>

<script>
import SearchBar from "../section/searchBar.vue";
export default {
  name: "BaseHeader",
  components: { SearchBar },
};
</script>

<style lang="scss" scoped>
header {
  height: 6.25rem;
  background-color: black;
  img {
    width: 7.125rem;
    margin-top: 0.3125rem;
  }
}
</style>
