<template>
      <div class="row">
        <h5>Film Popolari:</h5>
        <Card class="col-3" v-for="film in movie" :key="film.id"
        :poster_path="film.poster_path"
        :title="film.title"
        :original_title="film.original_title"
        :original_language="film.original_language"
        :vote_average="film.vote_average"
        />
      </div>
</template>

<script>
import Card from "./Card.vue";

export default {
  name: "Main",
  props: {
    movie: Array,
    search2: Array,
  },
  components: {
    Card
  },

};
</script>

<style lang="scss" scoped>

  h5 {
    color: white;
    margin-top: 15px;
  }

</style>
