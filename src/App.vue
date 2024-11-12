<template>
  <Navbar/>
  <Intro />
  <Projects />
</template>

<script>
import Intro from './components/Intro.vue';
import Navbar from './components/Navbar.vue'
import Projects from './components/Projects.vue';

export default {
  name: 'App',
  components: {
    Navbar, Intro, Projects
  }
}
</script>

<style>
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
