<template>
  <div id="app">
    <Header :image="require('./assets/img/spotify-logo.png')" @genreFilter="showGenre"/>
    <Library :genre="selected_genre"/>
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
      selected_genre : ""
    }
  },

  methods: {
    showGenre(value) {
      this.selected_genre = value;
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
