<template>

  <div id="app">

    <Cards />

  </div>

</template>

<script>
  import Cards from './components/Cards.vue'

  export default {

    name: 'App',

    components: {

      Cards

    }

  }
</script>

<style  >
  @import './assets/fonts/font.scss';

  * {

    box-sizing: border-box;

  }

  html, body {

    width: 100%;
    height: 100%;
    margin: 0;
    overflow-x: hidden;

  }

  ul, h1, h2, h3, h4 {

    margin: 0;
    padding: 0;
    color: #343434;
    font-weight: 700;
    font-size: 14px;
    line-height: 24px;

  }

  li {

    list-style-type: none;

  }

  #app {

    width: 100%;
    height: 100%;

    font-family: 'Open Sans', 'Roboto', 'Arial', 'sans-serif';
    color: #343434;
    font-weight: 700;
    font-size: 14px;
    line-height: 24px;

  }

</style>
