<template>
  <div id="app">
    <Navbar @navigate="currentComponent = $event"></Navbar>
    <main>
      <component :is="currentComponent"></component>
    </main>
    <Footer></Footer>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import Portfolio from './components/Portfolio.vue';
import About from './components/About.vue';
import Projects from './components/Projects.vue'; 
import Footer from './components/Footer.vue';

export default {
  components: {
    Navbar,
    Portfolio,
    About,
    Projects, 
    Footer,
  },
  data() {
    return {
      currentComponent: 'Portfolio', 
    };
  },
};
</script>

<style>
#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

main {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
  background-color: #f0f0f0;
}

body {
  margin: 0;
  font-family: Arial, sans-serif;
}

footer {
  background-color: #333;
  color: white;
  text-align: center;
  padding: 10px 0;
}
</style>
