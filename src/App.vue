<template>
  <div id="app">
    <Header />
    <router-view/>
    <Footer />
  </div>
</template>

<script>
import Header from '@/components/shared/Header.vue'
import Footer from '@/components/shared/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    Footer
  }
}

</script>

<style>
  #app {
    display: flex;
    flex-flow: column nowrap;
    justify-content: space-between;

    min-height: 98vh;
  }
</style>
