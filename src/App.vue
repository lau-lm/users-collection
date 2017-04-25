<template>
  <div id="app" class="grey lighten-4">
    <router-view> </router-view>

    <navbar></navbar>

    <liste> </liste>

    <footer-materialize></footer-materialize>

  </div>
</template>

<script>
  import Navbar from './components/Navbar.vue'
  import Footer from './components/Footer.vue'
  import Breadcrumb from './components/Breadcrumb.vue'
  import Liste from './components/Liste.vue'

  export default {
    name: 'app',
    components: { navbar: Navbar, footerMaterialize: Footer, breadcrumb: Breadcrumb, liste: Liste }
  }

</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }
</style>