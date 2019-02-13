<template>
  <div id="app">
    <p>{{vue_data}}</p>
    <HelloWorld msg="Welcome to My Vue.js Blog"/>
    <About />
    <Contact v-bind:prop='vue_data' />
    <Slides></Slides>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import Contact from './components/Contact.vue';
import About from './components/About.vue';
import Slides from './components/Slides.vue';

export default {
  name: 'app',
  components: {
    HelloWorld,
    Contact,
    About,
    Slides
  },
  data:function() {
    return {vue_data: "Vue's data from App.vue" }
  }
}
</script>

<style>
#app {
  font-family: 'Raleway', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
