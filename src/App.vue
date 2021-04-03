<template>
  <v-app app id="app">
    <Header />
    <router-view />
    <Footer />
  </v-app>
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