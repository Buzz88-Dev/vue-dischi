<template>
  <div id="app">
    <HeaderNav />
    <DiscsList />
  </div>
</template>

<script>
import HeaderNav from './components/Header.vue';
import DiscsList from './components/DiscsList.vue';

export default {
  name: 'App',
  components: {
    HeaderNav,
    DiscsList,
  }
}
</script>

<style lang="scss">

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 100%;
}
</style>
