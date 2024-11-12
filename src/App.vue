<template>
  <Navbar/>
  <Intro />
  <Projects />
  <Footer />
</template>

<script>
import Footer from './components/Footer.vue';
import Intro from './components/Intro.vue';
import Navbar from './components/Navbar.vue'
import Projects from './components/Projects.vue';

export default {
  name: 'App',
  components: {
    Navbar, Intro, Projects, Footer
  }
}
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Comfortaa:wght@300..700&family=Nunito:ital,wght@0,200..1000;1,200..1000&family=Playfair+Display:ital,wght@0,400..900;1,400..900&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap");
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
* {
  margin: 0;
  padding: 0;
  box-shadow: 0;
}
</style>
