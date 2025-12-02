<template>
 <NavBar :logo="logo_src" :alt="app_name"/>
  <router-view/>
  <Footer />
</template>

<script>
import NavBar from './components/NavBar.vue'
import Footer from './components/Footer.vue'
export default {
  components: {
    NavBar,
    Footer
  },
  data() {
    return {
      logo_src: '/img/BottlelabLogo.png',
      app_name: 'Make your own bottle'
    }
  }
}
</script>
<style>
  body {
    margin: 0;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    padding: 0;
    box-sizing: border-box;
  }

  .main-container {
    padding: 20px;
    min-height: 250px;
    margin: 50px;
  }

  h1 {
    text-align: center;
    font-size: 42px;
    margin-bottom: 30px;
    color: #222;
  }
</style>
