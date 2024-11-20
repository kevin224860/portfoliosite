<template>
  <nav class="navbar">
    <button class="menu-toggle" @click="menuOpen = !menuOpen">
      ☰
    </button>
    <ul class="nav-list links" :class="{ open: menuOpen }">
      <li class="nav-item link"><a href="#AboutMe">About Me</a></li>
      <li class="nav-item link"><a href="#MySkills">Skills</a></li>
      <li class="nav-item link"><a href="#MyExperience">Work Experience</a></li>
      <li class="nav-item link"><a href="#MyProjects">Projects</a></li>
      <!--<li class="nav-item link"><a href="#ContactMe">Contact Me</a></li>-->
      
    </ul>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      menuOpen: false
    };
  },
  methods: {
    navigateTo(section) {
      // Custom handling for navigation can be added here
      console.log(`Navigating to: ${section}`);
      this.menuOpen = false; // Close the menu after clicking a link
    }
  }
};
</script>

<style scoped>
.navbar {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1000;
  background-color: #1e1e2f;
  color: #fff;
  padding: 15px 30px;
}

.menu-toggle {
  display: none;
  background: none;
  border: none;
  font-size: 24px;
  color: #fff;
  cursor: pointer;
}

.nav-list {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  list-style: none; /* Removes bullets */
  padding: 0;
  margin: 0;
}

.nav-item {
  padding: 10px;
}

.link a {
  text-decoration: none; /* Removes underline */
  color: inherit;
  transition: color 0.3s ease;
}

.link a:hover {
  color: var(--primary-color);
  border-bottom: 2px solid var(--primary-color);
}

.link a:visited {
  color: inherit;
}

@media (max-width: 768px) {
  .menu-toggle {
    display: block; /* Shows menu toggle on small screens */
  }

  .nav-list {
    display: none;
    flex-direction: column;
    width: 100%;
    background-color: #1e1e2f;
  }

  .nav-list.open {
    display: flex;
  }

  .nav-item {
    text-align: center;
    padding: 15px 0;
  }
}
</style>
