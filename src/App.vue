<template>
  <div>
    
    <NavBar/>
    <AboutMe class="component-spacing" />
    <MySkills class="component-spacing" />
    <MyExperience class="component-spacing" />
    <MyProjects class="component-spacing" />
    <!--<ContactMe class="component-spacing" />-->
    
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue';
import AboutMe from './components/AboutMe.vue';
import MySkills from './components/MySkills.vue';
import MyExperience from './components/MyExperience.vue';
import MyProjects from './components/MyProjects.vue';
//import ContactMe from './components/ContactMe.vue';

export default {
  name: 'App',
  components: {
    NavBar,
    AboutMe,
    MySkills,
    MyExperience,
    MyProjects,
    //ContactMe
  }
}
</script>

<style>
:root {
  /* colors start */
  --bg-dark: #1b1c1d;
  --primary-color: #10dc80;
  --primary-hover-color: #b021bc;
  --secondary-color: #1e1e1e;
  --text-color: #fff;
  --text-secondary-color: #ccc;
  --background-color: #121212;
  --box-shadow-color: rgba(0, 0, 0, 0.3);
  background-color: var(--bg-dark);
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #fff;
  background-color: var(--bg-dark);
  width: 100%;
  height: 100%;
}

html {
  font-size: 13px;
  scroll-behavior: smooth;
}
.component-spacing {
  margin-top: 200px; /* Adds space below each component */
}

</style>
