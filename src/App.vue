<template>
  <div id="app">
    <Header :image="require('./assets/img/spotify-logo.png')" @genreFilter="showGenre" :genres="genresList"/>
    <Library :genre="selected_genre" @getGenres="getGenres"/>
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
      selected_genre : "",

      genresList: []
    }
  },

  methods: {
    showGenre(value) {
      this.selected_genre = value;
    },

    getGenres(array) {
      this.genresList = array
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
