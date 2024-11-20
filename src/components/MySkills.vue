<template>
  <section id="MySkills" class="my-skills">
    <div class="header-container">
      <h1>My Skills</h1>
    </div>
    <div class="skills-container">
      <div class="tabs">
        <button 
          v-for="(tab, index) in skillTabs" 
          :key="index" 
          @click="activeTab = tab.name" 
          :class="{ active: activeTab === tab.name }"
        >
          {{ tab.label }}
        </button>
      </div>

      <div v-for="(tab, index) in filteredTab" :key="index" class="tab-content">
        <ul>
          <li v-for="(skill, skillIndex) in tab.skills" :key="skillIndex">{{ skill }}</li>
        </ul>
        <div>
          <h2>{{ tab.label }}</h2>
          <p>{{ tab.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      activeTab: 'front-end',
      skillTabs: [
        {
          name: 'front-end',
          label: 'Front End',
          description: 'I work on the frontend using technologies like HTML and CSS to create user-friendly and responsive interfaces and am most experienced using javascript frameworks Vue and React.',
          skills: ['Vue.js', 'React', 'HTML/CSS']
        },
        {
          name: 'back-end',
          label: 'Back End',
          description: 'I work on the backend using technologies like Node.js, Spring Boot, and Laravel.',
          skills: ['Node.js', 'Spring Boot', 'Laravel']
        },
        {
          name: 'mobile',
          label: 'Mobile',
          description: 'For mobile development I focus on Android development but I have done some work with cross platform using flutter.',
          skills: ['Flutter', 'Kotlin', 'Java']
        },
        {
          name: 'cloud',
          label: 'Cloud',
          description: 'I work with cloud technologies such as AWS, Azure, and GCP to develop and manage scalable, secure, and high-performance cloud solutions. My primary focus is on AWS, where I leverage services like EC2 and Lambda functions.',
          skills: ['AWS', 'Azure', 'GCP']
        }
      ]
    };
  },
  computed: {
    filteredTab() {
      // Return only the tab that matches the activeTab
      return this.skillTabs.filter(tab => tab.name === this.activeTab);
    }
  }
};
</script>

<style scoped>

#MySkills{
  padding: 150px 20px;
}

.header-container {
  font-size: 26px;
  text-decoration: underline;
  width: 60%;
  margin: 0 auto 10px auto;
  text-align: left;
  color: var(--primary-color);
}
.my-skills {
  padding: 40px;
}
.skills-container {
  border-radius: 30px;
  padding: 30px;
  box-shadow: 5px 10px var(--primary-color);
  background: #2c2c3c;
  overflow: hidden;
  width: 60%;
  margin: 0 auto;
}
.tabs button {
  background: linear-gradient(to right, var(--primary-color), #64f1b2);
  width: 200px;
  height: 50px;
  padding: 10px;
  margin: 5px;
  cursor: pointer;
  border: none;
  font-size: 16px;
  border-radius: 6px;
  text-align: center;
  transition: background 0.3s, box-shadow 0.3s, transform 0.3s;
}
.tabs button:hover {
  background: linear-gradient(to right, #64f1b2, var(--primary-color));
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
  transform: scale(1.05);
}
.tabs button.active {
  color: var(--primary-color);
  background: #444;
  font-weight: bold;
}
.tab-content {
  margin-top: 25px;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 20px;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  color: #fff;
  margin-bottom: 5px;
}
</style>
