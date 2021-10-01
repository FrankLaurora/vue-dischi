<template>
  <div id="app">
    <Header :image="require('./assets/img/spotify-logo.png')"/>
    <Library/>
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
  }
}
</script>

<style lang="scss">
@import './assets/style/common.scss';

#app {
  color: #fff;
}
</style>
