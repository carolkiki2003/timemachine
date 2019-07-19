<template>
  <div id="app">
    <Home />
  </div>
</template>

<script>
  import Home from '@/pages/Home'
  export default {
    components: {
      Home
    }
  }
</script>

<style>
  @import './assets/normalize.scss';
  #app {
    font-family: 'Microsoft JhengHei', 'Apple LiGothic Medium', 'PMingLiU', 'sans-serif', 'serif';
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }
</style>
