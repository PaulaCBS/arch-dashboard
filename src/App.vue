<template>
  <div id="app">
    <Header />
    <router-view />
    <Footer />
  </div>
</template>

<script>
import Header from './components/shared/Header';
import Footer from './components/shared/Footer';

export default {
  name: 'App',

  components: {
    Header,
    Footer
  }
};
</script>

<style scoped>
  #app {
    display: flex;
    flex-flow: column nowrap;
    justify-content: space-between;
    min-height: 100vh;
    font-family: Roboto, sans-serif;
    background: #f7f7f7 url("./assets/images/background.jpg") center/cover;
  }
</style>