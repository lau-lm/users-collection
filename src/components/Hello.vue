<template>
  <div class="hello">

    <!--<navbar></navbar>

    <breadcrumb> </breadcrumb>
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>

    <liste> </liste>

    <footer-materialize></footer-materialize>-->

  </div>
</template>

<script>
  // import Navbar from './Navbar.vue'
  // import Footer from './Footer.vue'
  // import Breadcrumb from './Breadcrumb.vue'
  // import Liste from './Liste.vue'

  export default {
    name: 'hello',
    // components: { navbar: Navbar, footerMaterialize: Footer, breadcrumb: Breadcrumb, liste: Liste },
    data() {
      return {
        msg: 'Welcome to Your Vue.js App'
      }
    }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1,
  h2 {
    font-weight: normal;
  }
  
  ul {
    list-style-type: none;
    padding: 0;
  }
  
  li {
    display: inline-block;
    margin: 0 10px;
  }
  
  a {
    color: #42b983;
  }
</style>