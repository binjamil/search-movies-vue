<template>
  <div>
    <ul class="grid">
      <movie-list-item
        v-for="movie in movies"
        :movie="movie"
        :key="movie.imdbID"
      ></movie-list-item>
    </ul>
  </div>
</template>

<script>
import MovieListItem from "./MovieListItem";

export default {
  name: "movie-list",
  components: {
    MovieListItem
  },
  props: {
    movies: {
      type: Array,
      required: true
    }
  }
};
</script>

<style lang="scss" scoped>
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, 30rem);
  grid-column-gap: 6rem;
  grid-row-gap: 3rem;
  padding: 0;
  margin-top: 4rem;

  @media screen and (max-width: 600px) {
    grid-template-columns: repeat(auto-fill, 30rem);
    margin-top: 2rem;
  }
}
</style>
