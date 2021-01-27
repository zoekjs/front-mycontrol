<template>
  <div id="app">
    <navBar></navBar>
    <router-view/>
    <Footer></Footer>
  </div>
</template>

<script>
import navBar from "./components/Nav.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "app",
  components: {
    navBar,
    Footer
  }
}
</script>
