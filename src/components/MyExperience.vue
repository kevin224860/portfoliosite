<template>
  <section id="MyExperience" class="experience-container">
    <h1>Work Experience</h1>
    <div class="tabs">
      <button
        v-for="(experience, index) in experiences"
        :key="index"
        @click="activeTab = index"
        :class="['tab-button', { active: activeTab === index }]"
      >
        {{ experience.company }}
      </button>
    </div>

    <div class="tab-content" v-if="experiences[activeTab]">
      <h2>{{ experiences[activeTab].jobTitle }}</h2>
      <p><strong>Duration:</strong> {{ experiences[activeTab].duration }}</p>
      <ul>
        <li v-for="(task, index) in experiences[activeTab].responsibilities" :key="index">
          {{ task }}
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      activeTab: 0,
      experiences: [
        {
          company: "Ontario Power Generation (OPG)",
          jobTitle: "Software Developer Intern",
          duration: "Duration Placeholder", // Update with actual duration
          responsibilities: [
            "Collaborated on software solutions that improved workflow efficiencies.",
            "Developed and maintained code with high standards for reliability and performance.",
            "Assisted in the implementation of technical projects supporting energy systems.",
            "Participated in team meetings to discuss progress and future development."
          ]
        },
        {
          company: "Bucketlist Rewards and Recognition",
          jobTitle: "Software Developer Co-op",
          duration: "May 2022 - July 2022",
          responsibilities: [
            "Developed over 150 test cases for the QA team.",
            "Tested features and documented bugs using Jira.",
            "Built automation tasks using Python and Bash.",
            "Participated in Agile processes like standups and sprint planning."
          ]
        },
        {
          company: "eINSIGHT",
          jobTitle: "Software Developer Co-op",
          duration: "January 2022 - April 2022",
          responsibilities: [
            "Created and deployed data visualizations using Qlik Sense and MySQL.",
            "Completed user stories and bug fixes using Vue, Yii, and MySQL."
          ]
        }
      ]
    };
  }
};
</script>

<style scoped>


.experience-container {
  width: 80%;
  margin: 60px auto; /* Centers the container */
  padding: 20px;
  background-color: #1e1e2f;
  border-radius: 12px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.3);
  color: #fff;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  scroll-margin-top: 100px; /* Ensures the component is not flush with the top */
}


h1 {
  font-size: 2rem;
  text-align: left;
  margin-bottom: 20px;
  border-bottom: 2px solid var(--primary-color);
  padding-bottom: 10px;
}

.tabs {
  display: flex;
  gap: 10px;
  margin-bottom: 15px;
}

.tab-button {
  flex: 1;
  padding: 12px;
  cursor: pointer;
  border: none;
  background: #333;
  color: #fff;
  border-radius: 8px;
  transition: background 0.3s, transform 0.2s;
  font-weight: bold;
}

.tab-button:hover {
  background: #444;
  transform: translateY(-3px);
}

.tab-button.active {
  background: var(--primary-color);
  color: #fff;
}

.tab-content {
  padding: 20px;
  background: #2c2c3c;
  border-radius: 8px;
  box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.5);
}

h2 {
  font-size: 1.5rem;
  margin-top: 0;
}

ul {
  list-style-type: none; /* Removes the bullets */
  padding-left: 0; /* Adjusts the padding */
  margin-top: 10px;
}

li {
  margin-bottom: 10px;
}
</style>
