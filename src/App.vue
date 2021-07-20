<template>
  <div id="app">
    <Header @search="searchFilms"/>
    <Main :movie="search2" class="container"/>
    <Card/>

  </div>
</template>

<script>
import axios from "axios";
import Header from "@/components/Header.vue";
import Main from "@/components/Main.vue";
import Card from "@/components/Card.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
    Card
  },
  data: function () {
    return {
      movie: [],
      search2 : [],
    }
  },
  created () {
    axios.get("https://api.themoviedb.org/3/movie/popular?api_key=8cf49e8225a818c8b6106111d6e5001f&language=it=IT&page=1").then ((results) => {
      this.movie = results.data.results;
      this.search2 = results.data.results;
    })
  },
  methods: {
    searchFilms(searchFilm) {
      if (searchFilm.length === 0) {
        this.search2 = this.movie
        return;
      }
      axios.get(`https://api.themoviedb.org/3/search/multi?api_key=8cf49e8225a818c8b6106111d6e5001f&query=${searchFilm}`).then ((results) => {
        this.search2 = results.data.results;
      })
    },
  },
};
</script>

<style lang="scss" scoped>

@import url('https://fonts.googleapis.com/css2?family=Ubuntu:wght@400;500;700&display=swap');

#app {
  background-color: rgb(21, 21, 21);
  padding-bottom: 40px;
  font-family: 'Ubuntu', sans-serif;
  
  .container {
    margin: 0 auto;
  }
}

</style>
