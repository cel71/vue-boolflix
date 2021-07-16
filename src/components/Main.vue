<template>
    <div class="row">
        <Card class="col-2" v-for="film in results" :key="film.id"
        :Image="film.image"
        :title="film.title"
        :original_title="film.original_title"
        :original_language="film.original_language"
        :vote_average="film.vote_avarage"
    />
    </div>
</template>

<script>
import Card from "./Card.vue";

export default {
  name: "Main",
  props: {
    results: Array
  },
  components: {
    Card
  },

};
</script>

<style lang="scss" scoped>

</style>
