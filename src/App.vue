<template>
  <div id="app">
    <Header :image="require('./assets/img/spotify-logo.png')" @genreFilter="showGenre" :genres="genresList" @searchByArtist="showArtist"/>
    <Library :genre="selectedGenre" :artist="searchArtist" @getGenres="getGenres"/>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Library from './components/Library.vue'

export default {
  name: 'App',
  components: {
    Header,
    Library
  },

  data() {
    return {
      selectedGenre: "",

      genresList: [],

      searchArtist: ""
    }
  },

  methods: {
    showGenre(value) {
      this.selectedGenre = value;
    },

    getGenres(array) {
      this.genresList = array
    },

    showArtist(text) {
      this.searchArtist = text.toLowerCase()
    }
  }
}
</script>

<style lang="scss">
@import './assets/style/common.scss';

#app {
  color: #fff;
}
</style>
